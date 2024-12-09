# Single Element in a Sorted Array

## Problem Description
You are given a sorted array consisting of only integers where every element appears exactly twice, except for one element which appears exactly once. Return the single element that appears only once.

### Constraints
- Your solution must run in `O(log n)` time and `O(1)` space.

### Example
**Input:**
```plaintext
nums = [1,1,2,3,3,4,4,8,8]
```
**Output:**
```plaintext
2
```

**Input:**
```plaintext
nums = [3,3,7,7,10,11,11]
```
**Output:**
```plaintext
10
```

---

## Approach 1: Naive Linear Search

### Algorithm
1. Iterate through the array.
2. For each element, count its occurrences using an inner loop.
3. If the count is `1`, return that number.

**Code:**

```java
import java.util.*;

public class tUf {
    public static int getSingleElement(int []arr) {
        // Size of the array:
        int n = arr.length;

        //Run a loop for selecting elements:
        for (int i = 0; i < n; i++) {
            int num = arr[i]; // selected element
            int cnt = 0;

            //find the occurrence using linear search:
            for (int j = 0; j < n; j++) {
                if (arr[j] == num)
                    cnt++;
            }

            // if the occurrence is 1 return ans:
            if (cnt == 1) return num;
        }

        //This line will never execute
        //if the array contains a single element.
        return -1;
    }

    public static void main(String args[]) {
        int[] arr = {4, 1, 2, 1, 2};
        int ans = getSingleElement(arr);
        System.out.println("The single element is: " + ans);

    }
}
```

---

## Approach 2: Hash Array

### Algorithm
1. Find the largest number (`maxi`) in the array.
2. Create a hash array of size `maxi + 1` to count frequencies.
3. Traverse the array to populate the hash array(to count frequnecy, In the HashMap, the key 4 has a value of 1, so 4 is returned as the result.).
4. Traverse the array again to find the unique element by checking the frequency in the hash array.

**Code:**

```java
import java.util.*;

public class tUf {
    public static int getSingleElement(int []arr) {
        //size of the array:
        int n = arr.length;

        // Find the maximum element:
        int maxi = arr[0];
        for (int i = 0; i < n; i++) {
            maxi = Math.max(maxi, arr[i]);
        }

        // Declare hash array of size maxi+1
        // And hash the given array:
        int[] hash = new int[maxi + 1];
        for (int i = 0; i < n; i++) {
            hash[arr[i]]++;
        }

        //Find the single element and return the answer:
        for (int i = 0; i < n; i++) {
            if (hash[arr[i]] == 1)
                return arr[i];
        }

        //This line will never execute
        //if the array contains a single element.
        return -1;
    }

    public static void main(String args[]) {
        int[] arr = {4, 1, 2, 1, 2};
        int ans = getSingleElement(arr);
        System.out.println("The single element is: " + ans);

    }
}
```

---

## Approach 3: HashMap

### Algorithm
1. Create a `HashMap` to store the frequency of each number.
2. Traverse the array and populate the map.
3. Traverse the map to find the key with a value of `1`.

**Code:**

```java
import java.util.*;

public class tUf {
    public static int getSingleElement(int []arr) {
        //size of the array:
        int n = arr.length;

        // Declare the hashmap.
        // And hash the given array:
        HashMap<Integer, Integer> mpp = new HashMap<>();
        for (int i = 0; i < n; i++) {
            int value = mpp.getOrDefault(arr[i], 0);
            mpp.put(arr[i], value + 1);
        }

        //Find the single element and return the answer:
        for (Map.Entry<Integer, Integer> it : mpp.entrySet()) {
            if (it.getValue() == 1) {
                return it.getKey();
            }
        }

        //This line will never execute
        //if the array contains a single element.
        return -1;
    }

    public static void main(String args[]) {
        int[] arr = {4, 1, 2, 1, 2};
        int ans = getSingleElement(arr);
        System.out.println("The single element is: " + ans);

    }
}
```

---

## Complexity Comparison

| Approach      | Time Complexity | Space Complexity |
|---------------|-----------------|------------------|
| Naive Linear  | O(n^2)          | O(1)             |
| Hash Array    | O(n)            | O(maxi)          |
| HashMap       | O(n)            | O(n)             |

---

## Optimal Solution (Binary Search)

To meet the `O(log n)` time complexity requirement, a binary search approach is used:
1. Leverage the sorted nature of the array.
2. Use binary search to locate the unique element by checking the parity of indices.

### Complexity
- **Time Complexity:** `O(log n)` for binary search.
- **Space Complexity:** `O(1)`.
