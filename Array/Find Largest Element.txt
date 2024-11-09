PROBLEM:
Given an array arr[]. The task is to find the largest element and return it.

Examples:

Input: arr = [1, 8, 7, 56, 90]
Output: 90
Explanation: The largest element of the given array is 90.
Input: arr = [5, 5, 5, 5]
Output: 5
Explanation: The largest element of the given array is 5.
Input: arr = [10]
Output: 10
Explanation: There is only one element which is the largest.
________________________________________________________________________________________________________________________________

CODE:

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
________________________________________________________________________________________________________________________________

NOTES:
1)Consider first as largest
2)Loop through array from a[1]
3)Check if any of those is greater than largest switch largest with current
