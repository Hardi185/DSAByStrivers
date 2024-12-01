# Algorithm Complexity: Time and Space

## Time Complexity
Time complexity is a measure of the time an algorithm takes to complete as a function of the input size, `n`. It reflects how the execution time grows as the input size increases.

### Common Time Complexities:
| Complexity     | Description                           | Example                              |
|----------------|---------------------------------------|--------------------------------------|
| **O(1)**       | Constant time                         | Accessing an element in an array    |
| **O(log n)**   | Logarithmic time                      | Binary search                       |
| **O(n)**       | Linear time                           | Iterating through an array          |
| **O(n log n)** | Linearithmic time                     | Merge Sort, Quick Sort (average)    |
| **O(n²)**      | Quadratic time                        | Nested loops (e.g., Bubble Sort)    |
| **O(2ⁿ)**      | Exponential time                      | Recursive algorithms (e.g., Fibonacci) |
| **O(n!)**      | Factorial time                        | Permutation generation              |

### Algorithm Notation: Big O, Θ, and Ω

#### 1. **Big O (O): Upper Bound**
- Represents the worst-case scenario.
- Describes the **maximum growth rate** of an algorithm as input size increases.
- Helps analyze how slow an algorithm can be in the worst conditions.

**Example**:  
- Sorting algorithms like QuickSort have a worst-case complexity of **O(n²)** when the pivot selection leads to highly unbalanced partitions.

#### 2. **Theta (Θ): Tight Bound**
- Represents the **average case** when the algorithm has a consistent growth rate.
- Describes the algorithm's performance in typical scenarios.

**Example**:  
- Searching in a balanced binary search tree has an average-case complexity of **Θ(log n)**.

#### 3. **Omega (Ω): Lower Bound**
- Represents the best-case scenario.
- Describes the **smallest growth rate** for a given algorithm.

**Example**:  
- Searching in an unsorted array has a best-case complexity of **Ω(1)** when the target is the first element.

#### Comparison Table

| Notation   | Meaning                     | Example                              |
|------------|-----------------------------|--------------------------------------|
| **Big O**  | Upper bound (worst case)    | QuickSort: **O(n²)** (worst case)    |
| **Theta**  | Tight bound (average case)  | Balanced Binary Search Tree: **Θ(log n)** |
| **Omega**  | Lower bound (best case)     | Unsorted Array Search: **Ω(1)**     |


---

## Space Complexity
Space complexity measures the amount of memory an algorithm uses as a function of `n`, considering:
1. **Auxiliary space**: Extra memory used by the algorithm.
2. **Input size**: Memory used to store the input.

### Factors Affecting Space Complexity:
- **Variables**: Memory required for variables used in the algorithm.
- **Function Call Stack**: Memory required for recursive function calls.
- **Data Structures**: Memory required for arrays, lists, hash tables, etc.

### Example Space Complexities:
| Complexity     | Description                           | Example                              |
|----------------|---------------------------------------|--------------------------------------|
| **O(1)**       | Constant space                        | Iterative algorithms without extra storage |
| **O(n)**       | Linear space                          | Storing input in arrays or lists    |
| **O(n²)**      | Quadratic space                       | 2D arrays or matrices               |

---

## Why It Matters
Understanding time and space complexity is crucial for:
1. Writing efficient algorithms.
2. Optimizing resource usage (time and memory).
3. Comparing different approaches to solving a problem.

--- 

## References
- [Big-O Cheat Sheet](https://www.bigocheatsheet.com/)
- [Big O, Θ, and Ω Explained](https://www.geeksforgeeks.org/analysis-of-algorithms-set-2-asymptotic-analysis/)
- [Understanding Time Complexity](https://www.geeksforgeeks.org/understanding-time-complexity-simple-examples/)
