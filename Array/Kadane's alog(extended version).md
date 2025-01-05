# PROBLEM:

Given an array arr[], with 0-based indexing, select any two indexes, i and j such that i < j. From the subarray arr[i...j], select the smallest and second smallest numbers and add them, you will get the score for that subarray. Return the maximum possible score across all the subarrays of array arr[].

```yaml
Input : arr[] = [4, 3, 1, 5, 6]
Output : 11
Explanation : Subarrays with smallest and second smallest are:- [4, 3] smallest = 3,second smallest = 4
[4, 3, 1] smallest = 1, second smallest = 3
[4, 3, 1, 5] smallest = 1, second smallest = 3
[4, 3, 1, 5, 6] smallest = 1, second smallest = 3
[3, 1] smallest = 1, second smallest = 3
[3, 1, 5] smallest = 1, second smallest = 3
[3, 1, 5, 6] smallest = 1, second smallest = 3
[1, 5] smallest = 1, second smallest = 5
[1, 5, 6] smallest = 1, second smallest = 5
[5, 6] smallest = 5, second smallest = 6
Maximum sum among all above choices is, 5 + 6 = 11.

Input : arr[] = [5, 4, 3, 1, 6] 
Output : 9
```

---

## CODE:
```java
class Solution {
    public int pairWithMaxSum(int[] arr) {
        int maxScore = Integer.MIN_VALUE; // Initialize to the smallest integer value
        int firstMin = Integer.MAX_VALUE;
        int secondMin = Integer.MAX_VALUE;
        
        // Iterate through all subarrays
        for (int i = 0; i < arr.length - 1; i++) {
            // Variables to track the two smallest values
            
            
            for (int j = i; j < arr.length; j++) {
                // Update the two smallest numbers for the current subarray arr[i...j]
                if (arr[j] < firstMin) {
                    secondMin = firstMin; // Update second smallest
                    firstMin = arr[j]; // Update smallest
                } else if (arr[j] < secondMin && arr[j] != firstMin) {
                    secondMin = arr[j]; // Update second smallest only if it's different from firstMin
                }
                
                // Only calculate score if we have found at least two distinct elements
                //if (firstMin != Integer.MAX_VALUE && secondMin != Integer.MAX_VALUE) {
                    int score = firstMin + secondMin;
                    if(score > maxScore)
                    {
                        maxScore = score; // Update max score
                    }
                //}
            }
        }
        
        return maxScore; // Return the maximum score found
    }
    
}
```

