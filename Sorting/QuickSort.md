```java
import java.util.Arrays;

class Solution {

    public static void quickSort(int[] arr, int low, int high) {
        System.out.println("low: " + low + ", high: " + high + ", array initial: " + Arrays.toString(arr));
        if (low < high) {
            int pivotIndex = partition(arr, low, high);
            System.out.println("pivotIndex: " + pivotIndex);

            System.out.println("low and high for left subarray: " + low + ", " + (pivotIndex - 1));
            quickSort(arr, low, pivotIndex - 1); // Sort left sub-array
            System.out.println("arr after left subArray: " + Arrays.toString(arr));

            System.out.println("low and high for right subarray: " + (pivotIndex + 1) + ", " + high);
            quickSort(arr, pivotIndex + 1, high); // Sort right sub-array
            System.out.println("arr after right subArray: " + Arrays.toString(arr));
        }
    }

    private static int partition(int[] arr, int low, int high) {
        System.out.println("low: " + low + ", high: " + high + ", array partition: " + Arrays.toString(arr));
        int pivot = arr[low]; // Choose the first element as pivot
        System.out.println("pivot: " + pivot);

        int i = low + 1; // Pointer to track the boundary of elements less than pivot
        System.out.println("i: " + i);

        for (int j = low + 1; j <= high; j++) {
            // If current element is smaller than or equal to pivot
            if (arr[j] < pivot) {
                System.out.println("enter condition arr[j] < pivot: ");
                swap(arr, i, j);
                System.out.println("after swapping array: " + Arrays.toString(arr));
                i++;
            }
        }
        swap(arr, low, i - 1); // Place the pivot in its correct position
        System.out.println("at the end of partition: " + Arrays.toString(arr));
        System.out.println("partition value: " + (i - 1));
        return i - 1;
    }

    private static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
}
````

---

### NOTES:
- highly efficient sorting algorithm that employs a divide-and-conquer strategy
- It works by selecting a 'pivot' element.
- partitions the other elements into two sub-arrays, according to whether they are less than or greater than the pivot
- considered faster than other O(n log n) algorithms like merge sort or heap sort.

HOW it works:
1)choose pivot
2)bring it to the middle of array by swapping(at this point we'll have all the smaller ones to the left and greater ones to the left)
3)repeat this for left and right both
