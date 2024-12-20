# Merge Sort Implementation in Java

This repository contains two implementations of Merge Sort in Java:
- **Recursive Merge Sort**
- **Iterative Merge Sort**

---

## **Recursive Merge Sort**

### **Overview**
Recursive Merge Sort divides the array into halves recursively, sorts each half, and then merges the sorted halves.

### **Code**
```java
import java.util.Arrays;

public class MergeSortRecursive {
    // Merge Sort (Recursive)
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = left + (right - left) / 2;

            // Recursively sort the two halves
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            // Merge the sorted halves
            merge(arr, left, mid, right);
        }
    }

    // Method to merge two sorted halves
    public static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        // Temporary arrays
        int[] L = new int[n1];
        int[] R = new int[n2];

        // Copy data to temp arrays
        for (int i = 0; i < n1; i++)
            L[i] = arr[left + i];
        for (int j = 0; j < n2; j++)
            R[j] = arr[mid + 1 + j];

        // Merge the temp arrays back into the original array
        int i = 0, j = 0, k = left;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }

        // Copy remaining elements of L[], if any
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Copy remaining elements of R[], if any
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }

    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};
        System.out.println("Original Array: " + Arrays.toString(arr));

        mergeSort(arr, 0, arr.length - 1);
        System.out.println("Sorted Array: " + Arrays.toString(arr));
    }
}
```

---

## **Iterative Merge Sort**

### **Overview**
Iterative Merge Sort uses a bottom-up approach by merging subarrays of increasing sizes until the entire array is sorted.

### **Code**
```java
import java.util.Arrays;

public class MergeSortIterative {
    // Merge Sort (Iterative)
    public static void mergeSort(int[] arr) {
        int n = arr.length;

        // Merge subarrays in bottom-up manner
        for (int currSize = 1; currSize < n; currSize *= 2) {
            for (int left = 0; left < n - currSize; left += 2 * currSize) {
                int mid = left + currSize - 1;
                int right = Math.min(left + 2 * currSize - 1, n - 1);

                // Merge subarrays [left..mid] and [mid+1..right]
                merge(arr, left, mid, right);
            }
        }
    }

    // Method to merge two sorted halves (same as recursive version)
    public static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        // Temporary arrays
        int[] L = new int[n1];
        int[] R = new int[n2];

        // Copy data to temp arrays
        for (int i = 0; i < n1; i++)
            L[i] = arr[left + i];
        for (int j = 0; j < n2; j++)
            R[j] = arr[mid + 1 + j];

        // Merge the temp arrays back into the original array
        int i = 0, j = 0, k = left;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }

        // Copy remaining elements of L[], if any
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Copy remaining elements of R[], if any
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }

    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};
        System.out.println("Original Array: " + Arrays.toString(arr));

        mergeSort(arr);
        System.out.println("Sorted Array: " + Arrays.toString(arr));
    }
}
```

---

## **Comparison**

| **Aspect**          | **Recursive Merge Sort**     | **Iterative Merge Sort**     |
|---------------------|------------------------------|------------------------------|
| **Time Complexity** | \(O(n \log n)\) (All cases) | \(O(n \log n)\) (All cases) |
| **Space Complexity**| \(O(n + \log n)\)           | \(O(n)\)                     |
| **Call Stack Usage**| Requires \(O(\log n)\)     | No call stack overhead       |
| **Practical Usage** | Commonly used               | Preferred for large inputs   |
