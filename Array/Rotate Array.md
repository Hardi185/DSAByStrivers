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

## Approach 1:
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

---

## Approach 2:
```java
import java.util.*;

public class Main {
  // Function to rotate the array
  public static void rotateArray(int[] arr, int n, int k, String direction) {
    if (n == 0)
      return;

    k = k % n; // Adjust k to ensure it is within the bounds of the array length
    if (k > n)
      return;

    if (direction.equalsIgnoreCase("left")) {
      // Left Rotation
      int[] temp = new int[k]; // Temporary array to store the first k elements
      for (int i = 0; i < k; i++) {
        temp[i] = arr[i];
      }
      for (int i = 0; i < n - k; i++) {
        arr[i] = arr[i + k];
      }
      for (int i = n - k; i < n; i++) {
        arr[i] = temp[i - n + k];
      }
    } else if (direction.equalsIgnoreCase("right")) {
      // Right Rotation
      int[] temp = new int[k]; // Temporary array to store the last k elements
      for (int i = 0; i < k; i++) {
        temp[i] = arr[n - k + i];
      }
      for (int i = n - 1; i >= k; i--) {
        arr[i] = arr[i - k];
      }
      for (int i = 0; i < k; i++) {
        arr[i] = temp[i];
      }
    } else {
      System.out.println("Invalid direction! Use 'left' or 'right'.");
    }
  }

  public static void main(String[] args) {
    int[] arr = {1, 2, 3, 4, 5, 6, 7};
    int n = arr.length;
    int k = 2;

    // Rotate left
    System.out.println("Original Array: " + Arrays.toString(arr));
    rotateArray(arr, n, k, "left");
    System.out.println("After Left Rotation by " + k + ": " + Arrays.toString(arr));

    // Reset array
    arr = new int[]{1, 2, 3, 4, 5, 6, 7};

    // Rotate right
    rotateArray(arr, n, k, "right");
    System.out.println("After Right Rotation by " + k + ": " + Arrays.toString(arr));
  }
}
```

---

## Complexity Comparison:

| **Approach**      | **Time Complexity**                            | **Space Complexity**       | **Explanation**                                                                                                                                                  |
|--------------------|------------------------------------------------|-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Approach 1**    | \(O(k \cdot n)\)                               | \(O(1)\)                   | Each of the \(k\) rotations shifts all \(n\) elements in the array one position, leading to \(O(k \cdot n)\). Space usage is constant since no additional storage is used. |
| **Approach 2**    | \(O(n)\)                                       | \(O(k)\)                   | The rotation is achieved in three distinct passes: storing \(k\) elements in a temporary array, shifting the elements, and restoring the temporary array. This makes the time complexity \(O(n)\), while the temporary storage adds an \(O(k)\) space overhead. |
    
