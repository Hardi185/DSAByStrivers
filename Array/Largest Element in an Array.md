# Find the Largest Element in an Array

## Problem:
Given an array `arr[]`, the task is to find the largest element and return it.

### Examples:
- Input: arr = [1, 8, 7, 56, 90]
- Output: 90
- Explanation: The largest element of the given array is 90.

- Input: arr = [5, 5, 5, 5]
- Output: 5
- Explanation: The largest element of the given array is 5.

- Input: arr = [10]
- Output: 10
- Explanation: There is only one element which is the largest.

---

## Approach 1:

### Code:

```java
class Solution {
    public int largest(int[] arr) {
        int n = arr.length;
        
        int largest = arr[0];
        
        for (int i = 1; i < n; i++) {
            if (arr[i] > largest) {
                largest = arr[i];
            }
        }
        
        return largest; 
    }
}
```

### Algo:
1) Consider first as largest.
2) Loop through array from `arr[1]`.
3) Check if any of those is greater than largest, switch largest with current.

---

## Approach 2:

### Code:

```java

import java.util.*;
public class Solution {
 
  public static void main(String args[]) {
 
    int arr1[] =  {2,5,1,3,0};
    System.out.println("The Largest element in the array is: " + sort(arr1));
   
    int arr2[] =  {8,10,5,7,9};
    System.out.println("The Largest element in the array is: " + sort(arr2));
  }
  static int sort(int arr[]) {
    Arrays.sort(arr);
    return arr[arr.length - 1];
  }
}
```

### Algo:
1) Sort the Array.
2) Return the last index element.
