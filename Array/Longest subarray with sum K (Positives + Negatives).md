PROBLEM:
Given an array arr[] containing integers and an integer k, your task is to find the length of the longest subarray where the sum of its elements is equal to the given value k. It is guaranteed that a valid subarray exists.
Examples:

Input: arr[] = [10, 5, 2, 7, 1, 9], k = 15
Output: 4
Explanation: The subarray [5, 2, 7, 1] has a sum of 15 and length 4.
Input: arr[] = [-1, 2, 3], k = 6
Output: 0
Explanation: There is no subarray with a sum of 6.
Input: arr[] = [1, -1, 5, -2, 3], k = 3
Output: 4
Explanation: The subarray [1, -1, 5, -2] has a sum of 3 and length 4.
__________________________________________________________________________________________________________________________
CODE:
 class Solution {

    public static int lenOfLongestSubarr(int[] arr, int k) {
        // HashMap to store the cumulative sum and its first occurrence index
        HashMap<Integer, Integer> sumMap = new HashMap<>();
        int currentSum = 0;
        int maxLength = 0;

        // Initialize with sum 0 at index -1 to handle cases where subarray starts from index 0
        sumMap.put(0, -1);

        // Iterate over the array
        for (int i = 0; i < arr.length; i++) {
            // Update the current cumulative sum
            currentSum += arr[i];

            // Check if the current cumulative sum minus k has been seen before
            if (sumMap.containsKey(currentSum - k)) {
                // Calculate the length of the subarray
                int subarrayLength = i - sumMap.get(currentSum - k);
                maxLength = Math.max(maxLength, subarrayLength);
            }

            // Store the first occurrence of currentSum in the map
            if (!sumMap.containsKey(currentSum)) {
                sumMap.put(currentSum, i);
            }
        }

        // Return the maximum length of subarray with sum k
        return maxLength;
    }
}
__________________________________________________________________________________________________________________________

