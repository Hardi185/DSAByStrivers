# PROBLEM:
- Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
- You may assume that each input would have exactly one solution, and you may not use the same element twice.
- You can return the answer in any order.

## Example 1:

**Input:** nums = [2,7,11,15], target = 9

**Output:** [0,1]

**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].

## Example 2:

**Input:** nums = [3,2,4], target = 6

**Output:** [1,2]

## Example 3:

**Input:** nums = [3,3], target = 6

**Output:** [0,1]

---

# CODE:
```java
public class Solution {
 public static int[] twoSum(int[] nums, int target) 
    {
        // Loop through each element in the array
        for (int i = 0; i < nums.length; i++) {
            // Start the inner loop from the next index
            for (int j = i + 1; j < nums.length; j++) {
                // Check if the two numbers add up to the target
                if (nums[i] + nums[j] == target) {
                    // Return the indices as an array
                    return new int[] { i, j };
                }
            }
        }
        // If no solution found (though the problem states there is always one)
        throw new IllegalArgumentException("No two sum solution");
    }
}
```
