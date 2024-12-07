PROBLEM:
Given an unsorted array of integers nums, return the length of the longest consecutive elements sequence.

You must write an algorithm that runs in O(n) time.

Example 1:
Input: nums = [100,4,200,1,3,2]
Output: 4
Explanation: The longest consecutive elements sequence is [1, 2, 3, 4]. Therefore its length is 4.

Example 2:
Input: nums = [0,3,7,2,5,8,4,6,0,1]
Output: 9

---

CODE:

```java
import java.util.Arrays;

class Solution {
    public int longestConsecutive(int[] nums) {
        Arrays.sort(nums);
        
        System.out.println("Sorted array: " + Arrays.toString(nums));

        if (nums.length == 0) return 0;

        int longestLength = 1; 
        int currentLength = 1; 
        
        for (int i = 1; i < nums.length; i++) {
            if (nums[i] == nums[i - 1]) {
                // Skip duplicates
                continue;
            } else if (nums[i] == nums[i - 1] + 1) {
                // Increment current sequence length
                currentLength++;
            } else {
                // Reset current sequence length
                longestLength = Math.max(longestLength, currentLength);
                currentLength = 1; // Restart count for a new sequence
            }
        }
        
        // Check last sequence length
        longestLength = Math.max(longestLength, currentLength);
        
        return longestLength;
    }
}
```

---

SOLUTION:
1)Sort the array
2)if array length is 0 then return with 0 
else intialize longestLength and currentLength as 1 (assuming min length will be 1)
3)Loop through array if we found duplicates skip the index,
else if adjacents are same then increment currentLength
else reset currentLength and update longestLength 
