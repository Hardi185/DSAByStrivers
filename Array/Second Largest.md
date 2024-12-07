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

---

## Approach 1:

### Algo:

- Sort the array in ascending order
- The element present at the second index from the end is the second largest element
  
**CODE:**

```java
import java.io.*;
import java.util.Arrays;
class Solution
{
static private void getElements(int[] arr, int n)
{
	if (n == 0 || n==1)
	{
		System.out.print(-1);
		System.out.print(" ");
		System.out.print(-1);
		System.out.print("\n");
	}
	Arrays.sort(arr);
	int small = arr[1];
	int large = arr[n - 2];
	System.out.println("Second smallest is "+small);
	System.out.println("Second largest is "+large);
}
public static void main(String[] args)
{
	int[] arr = {1, 2, 4, 6, 7, 5};
	int n = arr.length;
	getElements(arr, n);
}
}
```

## Approach 2:

### Algo:
- Initialize largest and second largest with MIN value
- Loop through array
- check if we found Largest while traversing till current, do given assignment
    - else if we found second largest while traversing till current, do given assignment 

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

## Complexity Comparison

| **Aspect**           | **Approach 1 (Sorting)**                                  | **Approach 2 (Iterative Comparison)**                      |
|-----------------------|----------------------------------------------------------|-----------------------------------------------------------|
| **Algorithm**         | Sort the array, then access the second last element       | Traverse the array while maintaining the largest and second-largest values |
| **Time Complexity**   | O(n log n) (due to sorting)                               | O(n) (single traversal)                                   |
| **Space Complexity**  | O(1) if sorting is in-place, otherwise O(n)              | O(1)                                                     |
| **Efficiency**        | Less efficient for this task                             | More efficient for this task                              |

