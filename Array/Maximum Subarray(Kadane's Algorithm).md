# PROBLEM:
Given an integer array nums, find the 
subarray with the largest sum, and return its sum.

```yaml
Example 1:
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: The subarray [4,-1,2,1] has the largest sum 6.

Example 2:
Input: nums = [1]
Output: 1
Explanation: The subarray [1] has the largest sum 1.

Example 3:
Input: nums = [5,4,-1,7,8]
Output: 23
Explanation: The subarray [5,4,-1,7,8] has the largest sum 23.
```

---

## CODE:
```java
class Solution {
    public int maxSubArray(int[] nums) {
        int currentSum = nums[0];
        int maxSum = nums[0];
        
        for (int i = 1; i < nums.length; i++) {
            //if number is greater than the whole sum till now then number is currentSum
            currentSum = Math.max(nums[i], currentSum + nums[i]);
            if(currentSum > maxSum)
            {
                maxSum = currentSum;
            }
        }
        return maxSum;
    }
}
```

---

## SOLUTION:
1. Initialise currentSum and maxSum with first element
2. Loop through the array
3. First check max between currentSum and Value, have max as currentSum
4. If currentSum is Greater than maxSum then update maxSum
