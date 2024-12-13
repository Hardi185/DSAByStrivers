# Deleting a Node in a Doubly Linked List (DLL)

This project demonstrates how to delete a node from a **Doubly Linked List (DLL)** in three scenarios:
1. Delete the **first node**.
2. Delete the **last node**.
3. Delete a node at a **specific position**.

---

## Problem Statement
Implement functions to remove a node from a Doubly Linked List (DLL) while maintaining the structural integrity of the list.

---

## Features
- **Delete the First Node**: Removes the head node of the list.
- **Delete the Last Node**: Removes the last node of the list.
- **Delete at a Specific Position**: Removes a node at the desired position.

---

## Algorithm

### Delete the First Node:
1. If the list is empty, print an error message.
2. Update the head to point to the next node.
3. If the updated head is not null, set its `prev` pointer to null.

### Delete the Last Node:
1. If the list is empty, print an error message.
2. Traverse the list to find the last node.
3. Update the `next` pointer of the second-to-last node to null.

### Delete at a Specific Position:
1. If the position is invalid, print an error message.
2. Traverse the list to find the node at position `pos`.
3. Update the `next` pointer of the previous node and the `prev` pointer of the next node to bypass the node to be deleted.

---

## Code

```java
class Node {
    int data;
    Node prev, next;

    // Constructor to create a new node
    Node(int data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}

class DoublyLinkedList {
    Node head;

    // Delete the first node
    public void deleteFirst() {
        if (head == null) {
            System.out.println("List is empty. Cannot delete.");
            return;
        }
        head = head.next;
        if (head != null) {
            head.prev = null;
        }
    }

    // Delete the last node
    public void deleteLast() {
        if (head == null) {
            System.out.println("List is empty. Cannot delete.");
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        if (temp.prev != null) {
            temp.prev.next = null;
        } else {
            head = null; // If there's only one node
        }
    }

    // Delete at a specific position
    public void deleteAtPosition(int position) {
        if (head == null || position <= 0) {
            System.out.println("Invalid position or list is empty.");
            return;
        }

        Node temp = head;

        // If the node to delete is the first node
        if (position == 1) {
            deleteFirst();
            return;
        }

        // Traverse to the node at the given position
        for (int i = 1; i < position; i++) {
            if (temp == null) {
                System.out.println("Position out of bounds.");
                return;
            }
            temp = temp.next;
        }

        // If the node to delete is the last node
        if (temp.next == null) {
            deleteLast();
            return;
        }

        // Remove the node by updating pointers
        temp.prev.next = temp.next;
        if (temp.next != null) {
            temp.next.prev = temp.prev;
        }
    }

    // Print the list
    public void printList() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }
}

public class Main {
    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        // Populate the list
        dll.head = new Node(5);
        dll.head.next = new Node(10);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(15);
        dll.head.next.next.prev = dll.head.next;

        System.out.println("Initial list:");
        dll.printList(); // Output: 5 10 15

        // Delete the first node
        dll.deleteFirst();
        System.out.println("After deleting the first node:");
        dll.printList(); // Output: 10 15

        // Delete the last node
        dll.deleteLast();
        System.out.println("After deleting the last node:");
        dll.printList(); // Output: 10

        // Delete at a specific position
        dll.insertAtEnd(20); // Adding a node for demonstration
        dll.deleteAtPosition(2);
        System.out.println("After deleting at position 2:");
        dll.printList(); // Output: 10
    }
}
```
