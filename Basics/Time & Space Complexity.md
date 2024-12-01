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
- [Understanding Time Complexity](https://www.geeksforgeeks.org/understanding-time-complexity-simple-examples/)
