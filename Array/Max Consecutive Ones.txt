PROBLEM:
Given a binary array nums, return the maximum number of consecutive 1's in the array.

Example 1:
Input: nums = [1,1,0,1,1,1]
Output: 3
Explanation: The first two digits or the last three digits are consecutive 1s. The maximum number of consecutive 1s is 3.

Example 2:
Input: nums = [1,0,1,1,0,1]
Output: 2
__________________________________________________________________________________________________________________________
CODE:
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int maxCount = 0; // To track the maximum count of consecutive 1s
        int currentCount = 0; // To track the current streak of 1s

        // Iterate through the array
        for (int num : nums) {
            if (num == 1) {
                currentCount++; // Increment count for a consecutive 1
            } else {
                // Update maxCount if currentCount is greater
                maxCount = Math.max(maxCount, currentCount);
                currentCount = 0; // Reset the current streak
            }
        }
        // Final check to update maxCount after the loop
        maxCount = Math.max(maxCount, currentCount);

        return maxCount;
    }
}

__________________________________________________________________________________________________________________________

NOTE:
1)Keep track of maxCount and currentCount intialize with 0
2)Loop through the array, if we found number 1 then increment the currentCount
else update maxcount and  re-intialize currentCount as 0
