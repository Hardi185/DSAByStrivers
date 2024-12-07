# Linked List Explained

A **Linked List** is a linear data structure where elements (called nodes) are stored in a sequence, and each node points to the next node in the list. Unlike arrays, linked lists do not require contiguous memory locations. Linked lists are dynamic and allow efficient insertion and deletion of elements.

## Types of Linked Lists:

1. **Singly Linked List (SLL)**: 
   - Each node contains **data** and a reference (or pointer) to the next node.

2. **Doubly Linked List (DLL)**:
   - Each node contains **data**, a reference to the next node, and a reference to the previous node.

3. **Circular Linked List**:
   - The last node points back to the first node, forming a circle.

## Singly Linked List (SLL)

In a Singly Linked List, each node contains:

- **Data**: The actual data stored in the node.
- **Next**: A reference to the next node in the list.

### Explanation:

- **Node Class**: Each node has two components: data (the value of the node) and next (a reference to the next node).
- **addNode Method**: Adds a node to the end of the list.
- **printList Method**: Traverses the linked list and prints each node's value.
- **Main Method**: Creates a linked list and adds some nodes.

## Doubly Linked List (DLL)

In a Doubly Linked List, each node has:

- **Data**: The actual data stored in the node.
- **Next**: A reference to the next node in the list.
- **Prev**: A reference to the previous node.

This allows for traversal in both directions: forward and backward.

### Explanation:

- **Node Class**: Each node has three components: data, next (reference to next node), and prev (reference to previous node).
- **addNode Method**: Adds a node to the end of the list. When a new node is added, the prev pointer of the new node is set to the previous last node.
- **printForward Method**: Traverses the list from head to tail, printing each node's value.
- **printBackward Method**: First, the list is traversed to find the last node. Then, it prints the list from tail to head by following the prev pointers.

## Advantages of Linked Lists:

- **Dynamic Size**: Linked lists grow and shrink in size easily by adding or removing nodes, without needing to resize an array.
- **Efficient Insertions/Deletions**: Inserting or deleting a node is O(1) if you have a reference to the node, unlike arrays which require shifting elements.

## Disadvantages:

- **Random Access**: Linked lists do not support random access like arrays. To access a particular element, you must traverse the list.
- **Extra Memory**: Each node requires extra memory to store the pointer (or pointers) to the next and/or previous nodes.

Linked lists are particularly useful when you need to frequently insert or delete elements, but they can be less efficient when random access is needed.

