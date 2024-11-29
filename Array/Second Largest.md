# PROBLEM:
Given an array arr[], return the second largest element from an array. If the second largest element doesn't exist then return -1.

**Note:** The second largest element should not be equal to the first largest.

## Examples:

**Input:** arr[] = [12, 35, 1, 10, 34, 1]

**Output:** 34

**Explanation:** The largest element of the array is 35 and the second largest element is 34.


**Input:** arr[] = [10, 10]

**Output:** -1

**Explanation:** The largest element of the array is 10 and the second largest element does not exist..

--

# CODE:

```java
class Solution {
    public int getSecondLargest(int[] arr) {
        int largest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;
        
        for (int num : arr){
            if(num > largest){
                secondLargest = largest;
                largest = num;
            }
            else if(num > secondLargest && num < largest){
                secondLargest = num; }
    
        }
        
        return (secondLargest == Integer.MIN_VALUE) ? -1 : secondLargest;
    }
}
```

---

# NOTES:
1)Initialize largest and second largest with MIN value
2)Loop through array
3)check if we found Largest while traversing till current, do given assignment
else if we found second largest while traversing till current, do given assignment 
