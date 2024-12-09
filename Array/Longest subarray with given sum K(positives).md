# Longest Subarray with Given Sum K (Positives)

## Problem Statement
Given an array and a sum `k`, find the length of the longest subarray that sums to `k`.

### Examples
#### Example 1:
**Input**:  
`N = 3, k = 5, array[] = {2,3,5}`

**Output**:  
`2`

**Explanation**:  
The longest subarray with sum `5` is `{2, 3}`. Its length is `2`.

#### Example 2:
**Input**:  
`N = 5, k = 10, array[] = {2,3,5,1,9}`

**Output**:  
`3`

**Explanation**:  
The longest subarray with sum `10` is `{2, 3, 5}`. Its length is `3`.

---

## Approaches

### Approach 1: Brute Force (Two Loops)
**Algorithm**:
1. Loop through the array with an outer loop (`i`).
2. Use an inner loop (`j`) to calculate the sum from `i` to `j`.
3. If the sum equals `k`, update the `maxLen`.

**Code**:
```java



import java.util.*;

public class tUf {
    public static int getLongestSubarray(int []a, long k) {
        int n = a.length; // size of the array.

        int len = 0;
        for (int i = 0; i < n; i++) { // starting index
            long s = 0; // Sum variable
            for (int j = i; j < n; j++) { // ending index
                // add the current element to
                // the subarray a[i...j-1]:
                s += a[j];

                if (s == k)
                    len = Math.max(len, j - i + 1);
            }
        }
        return len;
    }

    public static void main(String[] args) {
        int[] a = {2, 3, 5, 1, 9};
        long k = 10;
        int len = getLongestSubarray(a, k);
        System.out.println("The length of the longest subarray is: " + len);
    }
}
```

---

### Approach 2: Hash Map with Prefix Sum
**Algorithm**:
1. Maintain a prefix sum and a hash map (`preSumMap`) to store the first occurrence of each prefix sum.
2. For each index `i`:
    - Calculate `sum` as the prefix sum up to `i`.
    - Compute `rem = sum - k`.
    - If `rem` is found in `preSumMap`, calculate the length as `i - preSumMap[rem]`.
    - If `sum` is not in `preSumMap`, store it with its index.
3. Update `maxLen` accordingly.

**Code**:
```java
import java.util.*;

public class tUf {
    public static int getLongestSubarray(int []a, long k) {
        int n = a.length; // size of the array.

        Map<Long, Integer> preSumMap = new HashMap<>();
        long sum = 0;
        int maxLen = 0;
        for (int i = 0; i < n; i++) {
            //calculate the prefix sum till index i:
            sum += a[i];

            // if the sum = k, update the maxLen:
            if (sum == k) {
                maxLen = Math.max(maxLen, i + 1);
            }

            // calculate the sum of remaining part i.e. x-k:
            long rem = sum - k;

            //Calculate the length and update maxLen:
            if (preSumMap.containsKey(rem)) {
                int len = i - preSumMap.get(rem);
                maxLen = Math.max(maxLen, len);
            }

            //Finally, update the map checking the conditions:
            if (!preSumMap.containsKey(sum)) {
                preSumMap.put(sum, i);
            }
        }

        return maxLen;
    }

    public static void main(String[] args) {
        int[] a = {2, 3, 5, 1, 9};
        long k = 10;
        int len = getLongestSubarray(a, k);
        System.out.println("The length of the longest subarray is: " + len);
    }
}
```

**Execution for Approach 2 (Hash Map):**
| Index | Element | Sum (Prefix Sum) | Remaining (Sum - k) | Found in Map? | Update maxLen | Map Update |
|-------|---------|------------------|---------------------|---------------|---------------|------------|
| 0     | 2       | 2                | -8                  | No            | 0             | `{2: 0}`   |
| 1     | 3       | 5                | -5                  | No            | 0             | `{2: 0, 5: 1}` |
| 2     | 5       | 10               | 0                   | No            | 3 (i + 1)     | `{2: 0, 5: 1, 10: 2}` |
| 3     | 1       | 11               | 1                   | No            | 3             | `{2: 0, 5: 1, 10: 2, 11: 3}` |
| 4     | 9       | 20               | 10                  | Yes           | 4             | `{2: 0, 5: 1, 10: 2, 11: 3, 20: 4}` |

---

### Approach 3: Two Pointers (Sliding Window)
**Algorithm**:
1. Use two pointers (`left` and `right`) to maintain a window.
2. Increment `right` to expand the window and calculate the sum.
3. If the sum exceeds `k`, increment `left` to shrink the window until the sum is less than or equal to `k`.
4. If the sum equals `k`, calculate the window size as `right - left + 1` and update `maxLen`.

**Code**:
```java



import java.util.*;

public class Main {
    public static int getLongestSubarray(int []a, long k) {
        int n = a.length; // size of the array.

        int left = 0, right = 0; // 2 pointers
        long sum = a[0];
        int maxLen = 0;
        while (right < n) {
            // if sum > k, reduce the subarray from left
            // until sum becomes less or equal to k:
            while (left <= right && sum > k) {
                sum -= a[left];
                left++;
            }

            // if sum = k, update the maxLen i.e. answer:
            if (sum == k) {
                maxLen = Math.max(maxLen, right - left + 1);
            }

            // Move forward thw right pointer:
            right++;
            if (right < n) sum += a[right];
        }

        return maxLen;
    }

    public static void main(String[] args) {
        int[] a = {2, 3, 5, 1, 9};
        long k = 10;
        int len = getLongestSubarray(a, k);
        System.out.println("The length of the longest subarray is: " + len);
    }
}
```

| Step | Left | Right | Sum | Action Taken | maxLen |
|------|------|-------|-----|--------------|--------|
| 1    | 0    | 0     | 2   | `sum < k`, move `right` to 1 and add `a[1]`. | 0      |
| 2    | 0    | 1     | 5   | `sum < k`, move `right` to 2 and add `a[2]`. | 0      |
| 3    | 0    | 2     | 10  | `sum == k`, calculate length: `right - left + 1 = 3`. Update `maxLen = 3`. | 3      |
| 4    | 0    | 3     | 11  | `sum > k`, reduce `sum` by `a[0]` and move `left` to 1. | 3      |
| 5    | 1    | 3     | 9   | `sum < k`, move `right` to 4 and add `a[4]`. | 3      |
| 6    | 1    | 4     | 18  | `sum > k`, reduce `sum` by `a[1]` and move `left` to 2. | 3      |
| 7    | 2    | 4     | 15  | `sum > k`, reduce `sum` by `a[2]` and move `left` to 3. | 3      |
| 8    | 3    | 4     | 10  | `sum == k`, calculate length: `right - left + 1 = 2`. `maxLen` remains 3 (no update). | 3      |
| 9    | 3    | 5 (end) | -  | `right` exceeds the array length. Stop loop. | 3      |

---

## Complexity Comparison

| Approach                | Time Complexity | Space Complexity |
|-------------------------|-----------------|------------------|
| Brute Force (Two Loops) | O(N^2)          | O(1)             |
| Hash Map (Prefix Sum)   | O(N)            | O(N)             |
| Two Pointers            | O(N)            | O(1)             |

---

