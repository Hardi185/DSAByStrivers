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
                    // Person i knows someone
                    iKnow[i]++;
                    //who person i knows
                    knowsMe[j]++; 
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
public class Main {

    // Function to find the celebrity
    public static int findCelebrity(int[][] arr, int n) {
        int top = 0, down = n - 1;

        // Narrow down the celebrity candidate using two pointers (top and down)
        while (top < down) {
            if (arr[top][down] == 1) {
                // top knows down, so top can't be a celebrity
                top++;
            } else if (arr[down][top] == 1) {
                // top doesn't know down, so down can't be a celebrity
                down--;
            }
            else if(arr[top][down] == 0 && arr[down][top] == 0){
                top++;
                down--;
            }
        }

        // Now top == down, we have a candidate at index top (or down)
        int candidate = top;

        // Verify if candidate is a celebrity
        for (int i = 0; i < n; i++) {
            // A celebrity knows no one (arr[candidate][i] should be 0 for all i != candidate)
            // Everyone knows the celebrity (arr[i][candidate] should be 1 for all i != candidate)
            if (i != candidate && (arr[candidate][i] == 1 || arr[i][candidate] == 0)) {
                return -1; // No celebrity found
            }
        }

        // If all checks passed, candidate is a celebrity
        return candidate;
    }

    public static void main(String[] args) {
        int[][] arr = {
            {0, 1, 0, 0},
            {0, 0, 0, 0},
            {1, 1, 0, 0},
            {0, 1, 0, 0}
        };

        int n = arr.length;
        int celebrity = findCelebrity(arr, n);
        
        if (celebrity == -1) {
            System.out.println("No celebrity found");
        } else {
            System.out.println("Celebrity is person at index: " + celebrity);
        }
    }
}
```

---

## Complexity comparision:

| **Metric**            | **Approach 1 (Brute Force)**                                    | **Approach 2 (Two Pointers)**                                     |
|-----------------------|------------------------------------------------------------------|-------------------------------------------------------------------|
| **Time Complexity**    | O(n²) (due to two nested loops for populating the `knowsMe` and `iKnow` arrays) | O(n) (due to the two-pointer technique reducing the problem to a linear scan) |
| **Space Complexity**   | O(n) (due to the additional arrays `knowsMe` and `iKnow` to store knowledge relationships) | O(1) (constant space is used, just two pointers)                   |
| **Efficiency**         | Slower for larger datasets due to nested loops.                 | Much faster, especially for larger datasets, due to linear complexity |
| **Verification Step**  | Requires checking all candidates against the conditions (O(n))  | Verification is done once after narrowing down the celebrity (O(n)) |

