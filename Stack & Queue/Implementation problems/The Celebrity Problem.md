# Celebrity Problem

The **Celebrity Problem** is a classic problem that involves determining a celebrity in a group of people based on their knowledge relationships. The problem is typically represented by a square matrix, where each cell indicates whether one person knows another person. The goal is to identify if there is a "celebrity" in the group who is known by everyone but knows no one.

## Problem Description

Given an `n x n` matrix `arr`, where:
- `arr[i][j] = 1` means person `i` knows person `j`.
- `arr[i][j] = 0` means person `i` does not know person `j`.

A **celebrity** is defined as a person who:
1. Is known by everyone in the group (i.e., their column in the matrix has `n-1` ones).
2. Knows no one (i.e., their row in the matrix has all zeros except for their own position).

The task is to determine if there is a celebrity in the group and, if so, return their index. If no celebrity exists, return `-1`.

### Example

Given the matrix:
![image](https://github.com/user-attachments/assets/78464b2b-3edb-4999-9e55-09de7a3f3036)

Here 1 will be celebrity because he knows no one --> that row is 0, everyone knows him --> that column is 1 excepting i==j

---

## Approach 1:
```java
class Main {
    // Function to find the celebrity
    public static int findCelebrity(int[][] arr, int n) {
        // Arrays to store the number of people each person knows and is known by
        int[] knowsMe = new int[n];  // knowsMe[i] = number of people that person i is known by
        int[] iKnow = new int[n];    // iKnow[i] = number of people person i knows
        
        // Populate the knowsMe and iKnow arrays
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (arr[i][j] == 1) {
                    iKnow[i]++;
                    knowsMe[j]++; 
                    // Person i knows person j
                }
            }
        }

        // Now find the celebrity, checking the conditions
        for (int i = 0; i < n; i++) {
            // Person i is a celebrity if:
            // - Person i knows no one (iKnow[i] == 0)
            // - Person i is known by everyone (knowsMe[i] == n-1)
            if (iKnow[i] == 0 && knowsMe[i] == n-1) {
                return i;  // Return the index of the celebrity
            }
        }

        // No celebrity found
        return -1;
    }

    public static void main(String[] args) {
        // Example input
        int[][] arr = {
            {0, 1, 0},
            {0, 0, 0},
            {1, 1, 0}
        };

        int n = arr.length;
        int celebrity = findCelebrity(arr, n);

        if (celebrity == -1) {
            System.out.println("No celebrity found.");
        } else {
            System.out.println("Celebrity is at index: " + celebrity);
        }
    }
}
```

## Approach 2:
```java
```

---

## Complexity comparision:

