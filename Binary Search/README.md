# Binary Search Explained

**Binary Search** is an efficient algorithm for finding an element in a sorted array (or list) by repeatedly dividing the search interval in half. The idea is to compare the target value to the middle element of the array:

- If the target value is equal to the middle element, you've found the target.
- If the target value is smaller than the middle element, narrow the search to the left half.
- If the target value is larger than the middle element, narrow the search to the right half.

Repeat this process until the target is found or the search interval is empty.

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

## Key Differences Between Iterative and Recursive Approaches

- **Iterative Approach**: Uses a `while` loop and modifies the low and high indices in place.
- **Recursive Approach**: Uses recursion, calling the function with updated low and high values until the base case is reached.
