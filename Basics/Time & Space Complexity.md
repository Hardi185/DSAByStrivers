# Algorithm Complexity: Time and Space

## Table of Contents
1. [Time Complexity](#time-complexity)  
   - [Common Time Complexities](#common-time-complexities)  
   - [Algorithm Notation: Big O, Θ, and Ω](#algorithm-notation-big-o-θ-and-Ω)  
     - [Big O (O): Upper Bound](#1-big-o-o-upper-bound)  
     - [Theta (Θ): Tight Bound](#2-theta-θ-tight-bound)  
     - [Omega (Ω): Lower Bound](#3-omega-Ω-lower-bound)  
   - [Key Points for Understanding Time Complexity](#key-points-for-understanding-time-complexity)  
2. [Space Complexity](#space-complexity)  
   - [Factors Affecting Space Complexity](#factors-affecting-space-complexity)  
   - [Example Space Complexities](#example-space-complexities)  
3. [Why It Matters](#why-it-matters)  
4. [References](#references)

---

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

### Key Points for Understanding Time Complexity

#### 1. Examine the Worst Case
- Always analyze the algorithm's behavior for the **largest possible input** or **most complex scenarios**.
- Worst-case analysis ensures the algorithm can handle any situation.

**Example**:  
- Searching in an array requires **O(n)** comparisons in the worst case when the target is at the end or not present.

#### 2. Ignore Constants
- Focus on the **growth rate** of the algorithm, not exact values or constant factors.
- Constants and lower-order terms become negligible as input size increases.

**Example**:  
- **O(3n + 5)** simplifies to **O(n)** because the growth rate is linear.

#### 3. Avoid Lower Bounds for Practical Design
- While lower bounds (best-case scenarios) are important, focusing on **upper bounds (worst-case scenarios)** ensures the algorithm is efficient under all conditions.

**Example**:  
- Designing for worst-case performance ensures robust algorithms, even for edge cases.

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
