PROBLEM:
You are given a sorted array consisting of only integers where every element appears exactly twice, except for one element which appears exactly once.

Return the single element that appears only once.

Your solution must run in O(log n) time and O(1) space.
Example 1:

Input: nums = [1,1,2,3,3,4,4,8,8]
Output: 2
Example 2:

Input: nums = [3,3,7,7,10,11,11]
Output: 10
____________________________________________________________________________________________________________________________________
CODE:
//binary search approach
public class Solution {
    public static int singleNonDuplicate(int[] arr) {
        int n = arr.length; // Size of the array.

        // Edge cases:
        if (n == 1)
            return arr[0];
        if (arr[0] != arr[1])
            return arr[0];
        if (arr[n - 1] != arr[n - 2])
            return arr[n - 1];

        int low = 1, high = n - 2;
        while (low <= high) {
            int mid = (low + high) / 2;

            // If arr[mid] is the single element:
            if (arr[mid] != arr[mid + 1] && arr[mid] != arr[mid - 1]) {
                return arr[mid];
            }

            // We are in the left:
            if ((mid % 2 == 1 && arr[mid] == arr[mid - 1])
                    || (mid % 2 == 0 && arr[mid] == arr[mid + 1])) {
                // Eliminate the left half:
                low = mid + 1;
            }
            // We are in the right:
            else {
                // Eliminate the right half:
                high = mid - 1;
            }
        }

        // Dummy return statement:
        return -1;
    }
}
____________________________________________________________________________________________________________________________________
SOLUTION:
--> Let us suppose we have array like this:
1, 1, 2, 2, 3, 3, 4, 5, 5, 6, 6


1)Now for first element 1 we need to compare with right element only, and for last element we need to compare with left element only
2)If we do not find any mismatch(both are equal) till now, we'll shrink the range from both the side(to reduce comparisions)
3)For all the element which are middle elements, we need to check this:
-->one thing we can observe if the single element 4 will not match the value from the element right to it and left to it
3 != 4, 4 != 5, when this case if find in mid element we'll return

-->if mid is not at that point(we discussed above), either we need to eliminate left half or right half, now how we'll decide that?
as we can observer this array can be seen based on indexes as:
(even, odd)(even, odd)(even, odd) 4 (odd, even)(odd, even)
based on indexes value we can say: 

-->we're on left half and ans will be on right half
if current index is even and value after that index is same or
if current index is odd and value before that index is same

-->we're on right half and ans will be on left half
if current index is odd and value after that index is same or
if current index is even and value before that index is same
