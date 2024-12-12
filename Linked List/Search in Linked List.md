# Linked List Key Search

This program solves the problem of checking if a given key is present in a singly linked list. The task is to search for a specific key in the linked list and return `true` if it is found, otherwise return `false`.

## Problem Statement

Given a singly linked list of `n` nodes and a key, the task is to check whether the key is present in the linked list or not.

### Example 1:
**Input**:
- Linked List: `1 -> 2 -> 3 -> 4`
- Key: `3`

**Output**:  
`True`  
**Explanation**: 3 is present in the linked list, so the function returns `true`.

### Example 2:
**Input**:
- Linked List: `5 -> 6 -> 7 -> 8`
- Key: `10`

**Output**:  
`False`  
**Explanation**: 10 is not present in the linked list, so the function returns `false`.

## Approach

The solution traverses the linked list starting from the head and compares each node's data with the given key. If the key is found in any node, it returns `true`. If the end of the list is reached without finding the key, it returns `false`.

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
    // Function to search for a key in the linked list
    static boolean searchKey(int n, Node head, int key) {
        // If the linked list is empty, return false
        if (head == null) {
            return false;
        }
        
        Node current = head;
        // Traverse the list for 'n' nodes
        for (int i = 0; i < n; i++) {
            // If key is found, return true
            if (current.data == key) {
                return true;
            }
            current = current.next; // Move to the next node
        }
        
        return false; // Key not found
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

        // Key to search in the linked list
        int key = 3;

        // Calling searchKey method from Solution class
        boolean found = Solution.searchKey(5, head, key);

        // Printing the result
        if (found) {
            System.out.println("Key " + key + " is found in the linked list.");
        } else {
            System.out.println("Key " + key + " is not found in the linked list.");
        }
    }
}
```

## EXPLANATION:

1. Check if the Linked List is Empty
2. Initialize the Current Node
3. Iterate Through the Linked List:
  - If key is found return true
  - else update current to next 
4. Return False if Key Not Found
