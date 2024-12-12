# Insert at the End of a Singly Linked List

## Problem Statement
Given the head of a Singly Linked List and a value `x`, insert the value `x` at the end of the linked list and return the modified linked list.

### Examples:

#### Example 1:
**Input:** 
LinkedList: `1->2->3->4->5`, `x = 6`

**Output:** 
`1->2->3->4->5->6`

**Explanation:** 
The value `6` is inserted at the end of the linked list.

---

#### Example 2:
**Input:** 
LinkedList: `5->4`, `x = 1`

**Output:** 
`5->4->1`

**Explanation:** 
The value `1` is inserted at the end of the linked list.

---

## Approach

To insert a value `x` at the end of a singly linked list, the following steps are performed:

1. Create a new node with value `x`.
2. Traverse the linked list to reach the last node.
3. Set the `next` pointer of the last node to point to the new node.
4. Return the head of the modified linked list.

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
    // Method to insert a node at the end of the linked list
    public static Node insertAtEnd(Node head, int x) {
        // Create a new node with the given value x
        Node newNode = new Node(x);
        
        // If the list is empty, the new node becomes the head
        if (head == null) {
            return newNode;
        }
        
        // Traverse to the last node
        Node current = head;
        while (current.next != null) {
            current = current.next;
        }
        
        // Link the last node to the new node
        current.next = newNode;
        
        // Return the head of the modified linked list
        return head;
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
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = new Node(4);
        head.next.next.next.next = new Node(5);
        
        int x = 6;
        head = insertAtEnd(head, x);
        System.out.print("Modified LinkedList: ");
        printList(head);

        // Example 2
        Node head2 = new Node(5);
        head2.next = new Node(4);
        
        int y = 1;
        head2 = insertAtEnd(head2, y);
        System.out.print("Modified LinkedList: ");
        printList(head2);
    }
}
```

---

## Explanation

### Steps to Insert a Value at the End of the Linked List:
1. **Create a New Node:**
   A new node is created using the given value `x`. This node will be added at the end of the linked list.

2. **Check if the List is Empty:**
   If the linked list is empty (`head == null`), the new node becomes the head of the linked list.

3. **Traverse the List:**
   If the list is not empty, traverse through the list until the last node is reached.

4. **Link the Last Node:**
   Set the `next` pointer of the last node to point to the new node.

5. **Return the Updated Head:**
   The head of the linked list is returned to reflect the updated structure.

---

## Complexity Analysis

### Time Complexity:
- **O(N):** Where `N` is the number of nodes in the linked list. This is because we traverse the list once to find the last node.

### Space Complexity:
- **O(1):** As we are not using any extra space apart from the new node.

---
