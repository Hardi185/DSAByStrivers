PROBLEM:
Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

Example 1:

Input: nums = [3,2,3]
Output: 3
Example 2:

Input: nums = [2,2,1,1,1,2,2]
Output: 2
_____________________________________________________________________________________________________________________________________________________________
CODE:
import java.util.HashMap;
import java.util.Map;

class Solution {
    public int majorityElement(int[] nums) {
        Map<Integer, Integer> countMap = new HashMap<>();
        
        for (int num : nums) {
            countMap.put(num, countMap.getOrDefault(num, 0) + 1);
        }

        int maxKey = -1;
        int maxValue = Integer.MIN_VALUE;

        for (Map.Entry<Integer, Integer> entry : countMap.entrySet()) {
            if (entry.getValue() > maxValue) {
                maxValue = entry.getValue();
                maxKey = entry.getKey();
            }
        }

        return maxKey;
    }
}
_____________________________________________________________________________________________________________________________________________________________
SOLUTION:
1)Intialize HashMap,number as key and count as value
2)Loop through the array,if key exists add the count else add new key
3)Initialize maxKey and maxValue with MIN_VALUE possible
4)Loop through the HashMap, check if current value is greater than maxValue
update maxKey and maxValue
5)Return maxKey
