# Pascal's Triangle Problem Variations

## Problem Statement

![pascal](https://github.com/user-attachments/assets/9e48f409-79ce-4aec-b615-e9ac3318da4b)

Pascal's Triangle is a triangular array where each number is the sum of the two numbers directly above it. It starts with a single `1` at the top. This problem has **three variations**:

1. **Variation 1**: Given row number `r` and column number `c`, print the element at position `(r, c)` in Pascal’s Triangle.
    - **Example**:
      Input: `r = 5, c = 3`  
      Output: `6`  
      Explanation: The element at position `(5, 3)` is `6`.

2. **Variation 2**: Given the row number `n`, print the entire `n-th` row of Pascal’s Triangle.
   - **Example**:
     Input: `n = 4`  
     Output: `[1, 3, 3, 1]`  
     Explanation: The 4th row of Pascal’s Triangle is `[1, 3, 3, 1]`.

3. **Variation 3**: Given the number of rows `n`,print the first `n` rows of Pascal’s Triangle.
   - **Example**:
     Input: `n = 3`  
     Output:  1 1 1 1 2 1
     
---

##  Variation 1: Pascal's Triangle Value at Position (r, c)

### 1) **Naive Approach: Generate the Entire Pascal’s Triangle**

In this approach, we generate the entire Pascal's Triangle up to the r-th row and c-th column and then return the element at the given position.

#### Algorithm Steps:
1. Create a list of lists (ArrayList of ArrayLists) to store Pascal’s Triangle.
2. Iterate through each row of the triangle, computing the values based on the values from the previous row.
3. Return the value at the position `(r-1, c-1)` as the triangle is zero-indexed.

#### Java Code (Naive Approach):

```java
import java.util.ArrayList;

public class PascalsTriangle {
    public static int getElementNaive(int r, int c) {
        // Generate Pascal's Triangle up to row r
        ArrayList<ArrayList<Integer>> triangle = new ArrayList<>();
        
        // Create each row of Pascal's Triangle
        for (int i = 0; i < r; i++) {
            ArrayList<Integer> row = new ArrayList<>();
            
            // Fill each row with the appropriate number of elements
            for (int j = 0; j <= i; j++) {
                if (j == 0 || j == i) {
                    row.add(1); // First and last elements of each row are 1
                } else {
                    // Sum of two values from the previous row
                    row.add(triangle.get(i - 1).get(j - 1) + triangle.get(i - 1).get(j));
                }
            }
            triangle.add(row);
        }
        
        // Return the element at position (r-1, c-1)
        return triangle.get(r - 1).get(c - 1);
    }

    public static void main(String[] args) {
        int r = 5, c = 3;
        System.out.println(getElementNaive(r, c)); // Output: 6
    }
}
```

#### Time and Space Complexity:
- **Time Complexity:** `O(r^2)`, because we generate `r` rows of Pascal's Triangle, and each row contains `i` elements, leading to a quadratic time complexity.
- **Space Complexity:** `O(r^2)`, as we store all the elements of the triangle in a 2D ArrayList.


### 2) Optimized Approach: Direct Calculation using Combination Formula

#### Algorithm Description

The combination formula is used to compute the binomial coefficient:

\[ C(n, r) = \frac{n!}{r! (n - r)!} \]

Where:
- `n` is the row number,
- `r` is the column number (position in the row).

The formula can be simplified and computed incrementally to avoid calculating full factorials. Instead of computing large factorials, the combination can be calculated iteratively by multiplying `n`, `(n-1)`, `(n-2)`, ..., down to `(n-r+1)` and dividing by `r!` incrementally.

#### Steps:
1. **Initialize a result variable** to 1.
2. **Iterate** from 1 to `r`, and in each iteration, update the result using the formula:
   \[
   C(n, r) = C(n, r) \times \frac{n - (r - 1)}{r}
   \]
3. **Return** the result when the loop finishes.

This approach allows for an efficient calculation without needing to calculate large factorials or generate the entire Pascal's Triangle.

#### Java Code (Naive Approach):

```java

public class Solution {
    public static long nCr(int n, int r) {
        long res = 1;

        // calculating nCr:
        for (int i = 0; i < r; i++) {
            res = res * (n - i);
            res = res / (i + 1);
        }
        return res;
    }

    public static int pascalTriangle(int r, int c) {
        int element = (int) nCr(r - 1, c - 1);
        return element;
    }

    public static void main(String[] args) {
        int r = 5; // row number
        int c = 3; // col number
        int element = pascalTriangle(r, c);
        System.out.println("The element at position (r,c) is: " + element);
    }
}  
        
```

#### Time Complexity: 
- **O(c)**  
  The optimized approach runs in linear time with respect to `c`, where `c` is the number of elements being processed.

#### Space Complexity: 
- **O(1)**  
  The space used is constant, as the algorithm only uses a fixed amount of space for variables, making it space-efficient.

### Comparison

| Approach             | Time Complexity | Space Complexity |
|----------------------|-----------------|------------------|
| Naive Approach       | O(r^2)          | O(r^2)           |
| Optimized Approach   | O(c)            | O(1)             |






