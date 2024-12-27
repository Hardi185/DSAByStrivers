# PROBLEM:
Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

```yaml
Example 1:
Input: nums = [1,2,3,4,5,6,7], k = 2 right
Output: [6,7,1,2,3,4,5]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]

Example 2:
Input: nums = [1,2,3,4,5,6,7], k = 2 left
Output: [3,4,5,6,7,1,2]
Explanation:
rotate 1 steps to the right: [2,3,4,5,6,7,1]
rotate 2 steps to the right: [3,4,5,6,7,1,2]
```

---

## CODE:
```java
class Solution {
    public void rotate(int[] nums, int k) {
        String direction = "left";
        int j = 0;
        while(j < k) {  
            System.out.println("while index: " + j);

            if(direction == 'l')
            {
                // Save the first element to put it at the last later
                int temp = nums[0];

                // Shift elements to the right
                for(int i = 1; i <= nums.length - 1; i++) {  
                    System.out.println("index: " + i + " value: " + nums[i]);
                    nums[i -1] = nums[i];
                    System.out.println("after switching: " + Arrays.toString(nums));
                }

                // Place the saved first element at the last position
                nums[nums.length - 1] = temp;
            }
            else{

                // Save the last element to put it at the start later
                int temp = nums[nums.length - 1];
            
                // Shift elements to the right
                for(int i = nums.length - 2; i >= 0 ; i--) {  
                    System.out.println("index: " + i + " value: " + nums[i]);
                    nums[i + 1] = nums[i];
                    System.out.println("after switching: " + Arrays.toString(nums));
                }

                // Place the saved last element at the first position
                nums[0] = temp;
            }

            // Print the modified array
            for (int i = 0; i < nums.length; i++) {
                System.out.print(nums[i] + " ");  // Print the modified nums array
            }
            System.out.println();  // New line for better readability
            
            j++;  // Increment 'j' to move to the next rotation
        }
    }
}
```

