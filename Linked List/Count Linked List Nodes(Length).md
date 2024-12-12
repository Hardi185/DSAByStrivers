# Linked List Length Finder

This program solves the problem of finding the length of a singly linked list. The length of the linked list is defined as the number of nodes it contains.

## Problem Statement

Given a singly linked list, the task is to find the length of the linked list, where the length is the number of nodes in the linked list.

### Example 1:
**Input**: `1 -> 2 -> 3 -> 4 -> 5`  
**Output**: `5`  
**Explanation**: The linked list contains 5 nodes.

### Example 2:
**Input**: `2 -> 4 -> 6 -> 7 -> 5 -> 1 -> 0`  
**Output**: `7`  
**Explanation**: The linked list contains 7 nodes.

![image](https://github.com/user-attachments/assets/59fc7272-bc4a-45f6-b640-fe3289e29e34)

## Approach

The solution traverses the linked list starting from the head and counts each node until the end of the list. The traversal stops when the `next` pointer is `null`, indicating the end of the list.

## Code Implementation

```java
class Node {
    int data;
    Node next;

    // Constructor to create a new node
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class Solution {
    // Function to count nodes of a linked list.
    public int getCount(Node head) {
        // If the list is empty, return 0
        if (head == null) {
            return 0;
        }
        
        // Initialize count and traverse the linked list
        int count = 1;
        Node current = head;
        while (current.next != null) {
            current = current.next;
            count++;
        }
        
        return count;
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating a linked list: 1 -> 2 -> 3 -> 4 -> 5
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = new Node(4);
        head.next.next.next.next = new Node(5);

        // Creating Solution instance to call getCount method
        Solution solution = new Solution();
        int length = solution.getCount(head);

        // Printing the length of the linked list
        System.out.println("Length of the linked list: " + length);
    }
}
```

### Algo:
Traverses the linked list from the head to the end, counting each node to determine the length.

