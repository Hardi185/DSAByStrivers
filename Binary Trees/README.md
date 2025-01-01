# Introduction to Binary Tree (BT)

A Binary Tree (BT) is a hierarchical data structure where each node has at most two children, commonly referred to as the left child and right child. It is widely used in various computer science applications such as searching, sorting, and expression evaluation.

## Basic Components of a Binary Tree

### Root
- The topmost node of the tree.
- **Example**: In a tree with nodes 10 → 20 → 30, the root is 10.

### Child
- The immediate descendants of a node.
- **Example**: For node 10, if 20 and 30 are connected as its children, they are 10's children.

### Ancestors
- All the nodes along the path from a node to the root.
- **Example**: For node 30, its ancestor is 10.

### Leaf
- A node with no children (i.e., both left and right child are null).
- **Example**: In a tree with nodes 10 → 20 → 30, node 30 is a leaf.

## Types of Binary Trees

### Full Binary Tree
- Every node either has 0 or 2 children (no node has only 1 child).

**Example:**
```
    10
   /  \
  20   30
 / \ 
40  50
```

### Complete Binary Tree
- All levels, except possibly the last, are completely filled, and all nodes in the last level are as far left as possible.

**Example:**
```
    10
   /  \
  20   30
 / \   /
40 50 60
```

### Perfect Binary Tree
- All internal nodes have 2 children, and all leaf nodes are at the same level.

**Example:**
```
    10
   /  \
  20   30
 / \   / \
40 50 60 70
```

### Balanced Binary Tree
- The height difference between the left and right subtrees of any node is at most 1.

**Example:**
```
    10
   /  \
  20   30
 / \
40  50
```

### Degenerate (or Skewed) Binary Tree
- Each parent node has only one child, making the tree behave like a linked list.

**Example (left-skewed):**
```
    10
   /
  20
 /
30
```

**Example (right-skewed):**
```
    10
      \
      20
        \
        30
```

## Summary
A binary tree is a foundational concept in computer science. Its structure and various types cater to different use cases, such as optimizing search operations, organizing data hierarchically, or constructing efficient algorithms for tasks like expression parsing or decision making.

