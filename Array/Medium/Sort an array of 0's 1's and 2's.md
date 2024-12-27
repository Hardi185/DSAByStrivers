# Problem Statement: 
Given an array consisting of only 0s, 1s, and 2s. Write a program to in-place sort the array without using inbuilt sort functions. ( Expected: Single pass-O(N) and constant space)

```yaml
Input: nums = [2,0,2,1,1,0]
Output: [0,0,1,1,2,2]

Input: nums = [2,0,1]
Output: [0,1,2]

Input: nums = [0]
Output: [0]
```

---

## Approach 1:
```java
import java.util.Arrays;

class Solution {
    public void sortColors(int[] nums) {
        Arrays.sort(nums); 
    }
}
```

---

## Approach 2:
```java

import java.util.*;

public class Main {
    public static void sortArray(ArrayList<Integer> arr, int n) {
        int cnt0 = 0, cnt1 = 0, cnt2 = 0;

        for (int i = 0; i < n; i++) {
            if (arr.get(i) == 0) cnt0++;
            else if (arr.get(i) == 1) cnt1++;
            else cnt2++;
        }

        //Replace the places in the original array:
        for (int i = 0; i < cnt0; i++) arr.set(i, 0); // replacing 0's

        for (int i = cnt0; i < cnt0 + cnt1; i++) arr.set(i, 1); // replacing 1's

        for (int i = cnt0 + cnt1; i < n; i++) arr.set(i, 2); // replacing 2's
    }

    public static void main(String args[]) {
        int n = 6;
        ArrayList<Integer> arr = new ArrayList<>(Arrays.asList(new Integer[] {0, 2, 1, 2, 0, 1}));
        sortArray(arr, n);
        System.out.println("After sorting:");
        for (int i = 0; i < n; i++) {
            System.out.print(arr.get(i) + " ");
        }
        System.out.println();

    }

}
```

---

## Approach 3:
```java
class Solution {
    public void sortColors(int[] nums) {
        int i;
        int n=nums.length;
        int a=0,b=0,c=0;
        for(i=0;i<n;i++)
        {
            if(nums[i]==0)
            {
                a++;b++;c++;
            }
            if(nums[i]==1)
            {
                b++;c++;
            }
            if(nums[i]==2)
                c++;
        }
        for(i=0;i<n;i++)
        {
            if(i<a)
                nums[i]=0;
            else if(i>=a&&i<b)
                nums[i]=1;
            else
                nums[i]=2;
        }
                        
        
        }
    }
```

---

## Approach 4:
```java
import java.util.*;

public class Main {
    public static void sortArray(ArrayList<Integer> arr, int n) {
        int low = 0, mid = 0, high = n - 1; // 3 pointers

        while (mid <= high) {
            if (arr.get(mid) == 0) {
                // Swap arr[low] and arr[mid]
                int temp = arr.get(low);
                arr.set(low, arr.get(mid));
                arr.set(mid, temp);

                low++;
                mid++;

            } else if (arr.get(mid) == 1) {
                mid++;

            } else {
                // Swap arr[mid] and arr[high]
                int temp = arr.get(mid);
                arr.set(mid, arr.get(high));
                arr.set(high, temp);

                high--;
            }
        }
    }

    public static void main(String args[]) {
        int n = 6;
        ArrayList<Integer> arr = new ArrayList<>(Arrays.asList(new Integer[] {0, 2, 1, 2, 0, 1}));
        sortArray(arr, n);
        System.out.println("After sorting:");
        for (int i = 0; i < n; i++) {
            System.out.print(arr.get(i) + " ");
        }
        System.out.println();
    }
}
```

### Algo:
```text
Algorithm SortArray(arr, n):
    low = 0
    mid = 0
    high = n - 1

    while mid <= high:
        if arr[mid] == 0:
            Swap arr[low] and arr[mid]
            Increment low by 1
            Increment mid by 1
        else if arr[mid] == 1:
            Increment mid by 1
        else:
            Swap arr[mid] and arr[high]
            Decrement high by 1

    Return sorted array
```

---

## Complexity comparision:

### Approach Time Complexity | Space Complexity

| **Approach**                            | **Time Complexity** | **Space Complexity** |
|-----------------------------------------|---------------------|----------------------|
| **Approach 1 (Using Arrays.sort())**    | `O(n log n)`        | `O(1)`               |
| **Approach 2 (Counting occurrences)**   | `O(n)`              | `O(1)`               |
| **Approach 3 (Using alternative counting)** | `O(n)`            | `O(1)`               |
| **Approach 4 (Dutch National Flag)**    | `O(n)`              | `O(1)`               |

