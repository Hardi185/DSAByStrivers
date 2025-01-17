# Problem:
- Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.
- You must implement a solution with a linear runtime complexity and use only constant extra space.

## Example 1:

**Input:** nums = [2,2,1]

**Output:** 1

## Example 2:

**Input:** nums = [4,1,2,1,2]

**Output:** 4

## Example 3:

**Input:** nums = [1]

**Output:** 1

---

# Code(Java):

```java
public class Solution {
    public static int singleNumber(int[] nums) {
        HashMap<Integer, Integer> numCounts = new HashMap<>();
        
        // Count the occurrences of each number
        for (int num : nums) {
            if (numCounts.containsKey(num)) {
                numCounts.put(num, numCounts.get(num) + 1);
            } else {
                numCounts.put(num, 1);
            }
        }
        
        // Find the number with count 1
        for (int num : numCounts.keySet()) {
            if (numCounts.get(num) == 1) {
                return num;  // Return the number that appears once
            }
        }
        
        return -1;  // In case no such number is found
    }
}
```
---

# Solution:
    1)User HashMap to store number as key and count as value

    2)Loop through the array, check if key already exists increment count or add new key

    3)Find key with count 1
