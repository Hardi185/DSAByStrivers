# Remove Duplicates from Sorted Array

## Problem Statement:
Given an integer array `nums` sorted in non-decreasing order, remove the duplicates **in-place** such that each unique element appears only once. The relative order of the elements should be kept the same. Return the number of unique elements, `k`.

### Constraints:
- The first `k` elements of `nums` must contain the unique elements in the original order.
- The remaining elements beyond `k` are not important.

---

## Example:

### Example 1:
**Input:**  
`nums = [1, 1, 2]`  
**Output:**  
`k = 2, nums = [1, 2, _]`  
**Explanation:**  
The first `k` elements are `[1, 2]`. It does not matter what comes beyond these.

### Example 2:
**Input:**  
`nums = [0, 0, 1, 1, 1, 2, 2, 3, 3, 4]`  
**Output:**  
`k = 5, nums = [0, 1, 2, 3, 4, _, _, _, _, _]`  
**Explanation:**  
The first `k` elements are `[0, 1, 2, 3, 4]`.

---

## Approaches:

### **Approach 1: Using a Set**

**Algorithm:**
1. Declare a `HashSet` (or `LinkedHashSet` to maintain insertion order).
2. Loop through the array and add each element to the set.  
   - Duplicates will automatically be removed.
3. Store the size of the set as `k`.
4. Copy the elements of the set back into the array starting from the beginning.

**Code:**

```java

import java.util.*;
public class Main {
    public static void main(String[] args) {
        int arr[] = {1,1,2,2,2,3,3};
        int k = removeDuplicates(arr);
        System.out.println("The array after removing duplicate elements is ");
        for (int i = 0; i < k; i++) {
            System.out.print(arr[i] + " ");
        }
    }
    static int removeDuplicates(int[] arr) {
        HashSet < Integer > set = new HashSet < > ();
        for (int i = 0; i < arr.length; i++) {
            set.add(arr[i]);
        }
        int k = set.size();
        int j = 0;
        for (int x: set) {
            arr[j++] = x;
        }
        return k;
    }
}
```

**Notes:**
- Use `LinkedHashSet` to preserve the original order of elements.
- The size of the set (`k`) is the number of unique elements.

---

### **Approach 2: Two Pointer Technique**

**Algorithm:**
1. Use two pointers, `i` and `j`, with both operating on the same array.
   - `i`: Tracks the position for unique elements (insertion index).
   - `j`: Traverses the array to compare elements.
2. For each element in `nums`:
   - If the current element (`nums[j]`) is not equal to the last inserted element (`nums[i]`), increment `i` and place the new unique element at index `i`.
3. Return `i + 1` as `k`, which represents the number of unique elements.

**Code:**

```java

import java.util.*;
public class Main {
    public static void main(String[] args) {
       int arr[] = {1,1,2,2,2,3,3};
        int k = removeDuplicates(arr);
        System.out.println("The array after removing duplicate elements is ");
        for (int i = 0; i < k; i++) {
            System.out.print(arr[i] + " ");
        }
    }
    static int removeDuplicates(int[] arr) {
        int i = 0;
        for (int j = 1; j < arr.length; j++) {
            if (arr[i] != arr[j]) {
                i++;
                arr[i] = arr[j];
            }
        }
        return i + 1;
    }
}
```


## Comparison of Approaches:

| **Aspect**         | **Approach 1 (Using Set)**           | **Approach 2 (Two Pointer)**       |
|---------------------|--------------------------------------|-------------------------------------|
| **Algorithm**       | Use a `HashSet` to remove duplicates | Use two pointers for in-place modification |
| **Time Complexity** | O(n) for iteration + O(n) for copying (overall O(n)) | O(n) (single traversal) |
| **Space Complexity**| O(n) for the set                   | O(1) (in-place)                    |
| **Best Use Case**   | When maintaining order is needed, but in-place modification is not crucial | When in-place modification is a requirement |
