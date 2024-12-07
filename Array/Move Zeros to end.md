PROBLEM:
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

Example 1:

Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
Example 2:

Input: nums = [0]
Output: [0]
________________________________________________________________________________________________________________________________

CODE:

class Solution {
    public void moveZeroes(int[] nums) {
        // Step 1: Initialize a pointer for the last non-zero element
        int lastNonZeroIndex = 0;

        // Step 2: Loop through the array
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) { // Check if the current element is non-zero
                // Place the non-zero element at the lastNonZeroIndex
                nums[lastNonZeroIndex] = nums[i];
                lastNonZeroIndex++; // Move the pointer to the right
            }
        }

        // Step 3: Fill the rest of the array with zeros
        for (int i = lastNonZeroIndex; i < nums.length; i++) {
            nums[i] = 0; // Set remaining positions to zero
        }
    }
}
__________________________________________________________________________________________________________________________

NOTES:
1)Intialize lastNonZeroIndex with 0 and loop through the array
2)if number is nonZero at it to the lastNonZeroIndex and increament count 
3)starting from lastNonZeroIndex to array length fill the rest of places with 0

Steps:
Before Array:[0, 1, 0, 3, 12]
Array in loop:[1, 1, 0, 3, 12]
Array in loop:[1, 3, 0, 3, 12]
Array in loop:[1, 3, 12, 3, 12]
After Array:[1, 3, 12, 0, 0]
