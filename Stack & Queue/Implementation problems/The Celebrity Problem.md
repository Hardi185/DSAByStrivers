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
```

## Approach 2:
```java
```

---

## Complexity comparision:

