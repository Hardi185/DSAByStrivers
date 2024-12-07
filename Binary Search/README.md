# Binary Search Explained

**Binary Search** is an efficient algorithm for finding an element in a sorted array (or list) by repeatedly dividing the search interval in half. The idea is to compare the target value to the middle element of the array:

- If the target value is equal to the middle element, you've found the target.
- If the target value is smaller than the middle element, narrow the search to the left half.
- If the target value is larger than the middle element, narrow the search to the right half.

Repeat this process until the target is found or the search interval is empty.

![binary-and-linear-search-animations](https://github.com/user-attachments/assets/3053f3be-5c97-4c06-97ad-c7bb43693bff)

## Why Binary Search is Efficient

- **Time Complexity**: O(log n), where `n` is the number of elements in the array. This is much faster than linear search, which has a time complexity of O(n), especially for large arrays.
- **Space Complexity**: O(1) for the iterative approach (constant space).

## Binary Search Algorithm

1. Initialize two pointers: `low` (starting from 0) and `high` (starting from the last index of the array).
2. Calculate the middle index: `mid = (low + high) / 2`.
3. Compare the element at the middle index with the target:
   - If they are equal, return the index.
   - If the target is smaller, adjust `high = mid - 1` to search the left half.
   - If the target is larger, adjust `low = mid + 1` to search the right half.
4. Repeat until `low` is greater than `high`, indicating the target is not in the array.

## Binary Search Code in Java (Iterative Approach)

```java
public class BinarySearch {

    // Binary Search function
    public static int binarySearch(int[] arr, int target) {
        int low = 0; // start index
        int high = arr.length - 1; // end index

        while (low <= high) {
            int mid = low + (high - low) / 2; // Calculate mid index to avoid overflow

            // Check if target is at mid
            if (arr[mid] == target) {
                return mid; // Target found, return index
            }

            // If target is smaller than mid, discard right half
            if (arr[mid] > target) {
                high = mid - 1;
            } else {
                // If target is larger than mid, discard left half
                low = mid + 1;
            }
        }
        
        // Target not found
        return -1; // return -1 if target is not found
    }

    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 7, 9, 11, 13, 15, 17, 19}; // Sorted array
        int target = 7; // Element to search for

        int result = binarySearch(arr, target);
        
        if (result == -1) {
            System.out.println("Element not found.");
        } else {
            System.out.println("Element found at index: " + result);
        }
    }
}
```

## Binary Search in Java (Recursive Approach)

```java
public class BinarySearch {

    // Recursive Binary Search function
    public static int binarySearchRecursive(int[] arr, int low, int high, int target) {
        if (low > high) {
            return -1; // Target not found
        }

        int mid = low + (high - low) / 2; // Calculate mid index

        // Check if target is at mid
        if (arr[mid] == target) {
            return mid; // Target found, return index
        }

        // If target is smaller than mid, search in the left half
        if (arr[mid] > target) {
            return binarySearchRecursive(arr, low, mid - 1, target);
        } else {
            // If target is larger than mid, search in the right half
            return binarySearchRecursive(arr, mid + 1, high, target);
        }
    }

    public static void main(String[] args) {
        int[] arr = {1, 3, 5, 7, 9, 11, 13, 15, 17, 19}; // Sorted array
        int target = 7; // Element to search for

        int result = binarySearchRecursive(arr, 0, arr.length - 1, target);
        
        if (result == -1) {
            System.out.println("Element not found.");
        } else {
            System.out.println("Element found at index: " + result);
        }
    }
}
```

## Key Differences Between Iterative and Recursive Approaches

- **Iterative Approach**: Uses a `while` loop and modifies the low and high indices in place.
- **Recursive Approach**: Uses recursion, calling the function with updated low and high values until the base case is reached.
