# Binary Search Tree (BST)

A Binary Search Tree (BST) is a type of binary tree in which each node follows these two conditions:

1. **Left Subtree Condition:** The left subtree of a node contains only nodes with values less than the node's value.
2. **Right Subtree Condition:** The right subtree of a node contains only nodes with values greater than the node's value.

This property ensures that for any given node:

- All nodes in its left subtree have smaller values.
- All nodes in its right subtree have larger values.

## Operations on BST

### 1. Insertion
Insert elements while maintaining the BST property: `left < root < right`.

### 2. Deletion
Remove a node while ensuring the tree remains a BST.

### 3. Search
Find a node by comparing values starting from the root.

## Example of BST

For a BST:

```
       10
      /  \
     5    20
    / \   / \
   3   7 15  25
```

- Nodes in the left subtree of `10` are less than `10` (e.g., `5, 3, 7`).
- Nodes in the right subtree of `10` are greater than `10` (e.g., `20, 15, 25`).

## Tree Traversal Methods

### 1. Preorder Traversal
In preorder traversal, the nodes are visited in the following order:

1. Visit the root node.
2. Traverse the left subtree.
3. Traverse the right subtree.

#### Example:
For the tree:

```
       10
      /  \
     5    20
    / \   / \
   3   7 15  25
```

Preorder traversal will be:
```
10 -> 5 -> 3 -> 7 -> 20 -> 15 -> 25
```

### 2. Postorder Traversal
In postorder traversal, the nodes are visited in the following order:

1. Traverse the left subtree.
2. Traverse the right subtree.
3. Visit the root node.

#### Example:
For the same tree:

```
       10
      /  \
     5    20
    / \   / \
   3   7 15  25
```

Postorder traversal will be:
```
3 -> 7 -> 5 -> 15 -> 25 -> 20 -> 10
```

### 3. Level-order Traversal (Breadth-First Traversal)
In level-order traversal, nodes are visited level by level starting from the root. Nodes on the same level are visited from left to right.

#### Example:
For the same tree:

```
       10
      /  \
     5    20
    / \   / \
   3   7 15  25
```

Level-order traversal will be:
```
10 -> 5 -> 20 -> 3 -> 7 -> 15 -> 25
```

This traversal is typically implemented using a queue.

## Summary of Traversal Orders

| Traversal  | Order of Visit                  |
|------------|---------------------------------|
| Preorder   | Root -> Left -> Right           |
| Postorder  | Left -> Right -> Root           |
| Level-order| Level by level, left to right   |

## Complexity of Traversals

- **Time Complexity:** O(n) for all three traversals, where `n` is the number of nodes in the tree.
- **Space Complexity:**
  - Preorder/Postorder: O(h), where `h` is the height of the tree (due to recursion stack).
  - Level-order: O(n) (queue size in worst case).

