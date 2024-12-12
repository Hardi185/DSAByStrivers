# Insert at the Head of a Singly Linked List

## Problem Statement
Given the head of a Singly Linked List and a value `x`, insert the value `x` at the head of the linked list and return the modified linked list.

### Examples:

#### Example 1:
**Input:** 
LinkedList: `2->3->4->5`, `x = 1`

**Output:** 
`1->2->3->4->5`

**Explanation:** 
The value `1` is inserted at the head of the linked list.

---

#### Example 2:
**Input:** 
LinkedList: `4->5`, `x = 3`

**Output:** 
`3->4->5`

**Explanation:** 
The value `3` is inserted at the head of the linked list.

---

## Approach

To insert a value `x` at the head of a singly linked list, the following steps are performed:

1. Create a new node with value `x`.
2. Set the `next` pointer of the new node to point to the current head.
3. Update the head to the new node.
4. Return the updated head of the linked list.

---

## Code Implementation

```java
class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class LinkedList {
    // Method to insert a node at the head of the linked list
    public static Node insertAtHead(Node head, int x) {
        // Create a new node with the given value x
        Node newNode = new Node(x);
        
        // Point the new node's next to the current head
        newNode.next = head;
        
        // Return the new node as the new head of the linked list
        return newNode;
    }

    // Method to print the linked list
    public static void printList(Node head) {
        Node current = head;
        while (current != null) {
            System.out.print(current.data + "->");
            current = current.next;
        }
        System.out.println("null");
    }

    public static void main(String[] args) {
        // Example 1
        Node head = new Node(2);
        head.next = new Node(3);
        head.next.next = new Node(4);
        head.next.next.next = new Node(5);
        
        int x = 1;
        head = insertAtHead(head, x);
        System.out.print("Modified LinkedList: ");
        printList(head);

        // Example 2
        Node head2 = new Node(4);
        head2.next = new Node(5);
        
        int y = 3;
        head2 = insertAtHead(head2, y);
        System.out.print("Modified LinkedList: ");
        printList(head2);
    }
}
```

---

## Explanation

### Steps to Insert a Value at the Head of the Linked List:
1. **Create a New Node:**
   A new node is created using the given value `x`. This node will be added at the head of the linked list.

2. **Set the Next Pointer:**
   The `next` pointer of the new node is set to point to the current head of the linked list.

3. **Update the Head:**
   The head of the linked list is updated to the new node.

4. **Return the Updated Head:**
   The head of the linked list is returned to reflect the updated structure.

---

## Complexity Analysis

### Time Complexity:
- **O(1):** Inserting at the head of the linked list is a constant-time operation.

### Space Complexity:
- **O(1):** As we are not using any extra space apart from the new node.

---
