# Doubly Linked List (DLL) Node Insertion

This project demonstrates how to insert a node into a **Doubly Linked List (DLL)** in three scenarios:
1. At the **beginning** of the list.
2. At the **end** of the list.
3. At a **specific position** in the list.

---

## Problem Statement
Implement functions to insert a new node into a Doubly Linked List (DLL) with efficient and concise algorithms for all three insertion scenarios. 

---

## Features
- **Insert at the Beginning**: Adds a node as the new head of the list.
- **Insert at the End**: Appends a node to the last position in the list.
- **Insert at a Specific Position**: Inserts a node at the desired position, maintaining the integrity of the list.

---

## Algorithm

### Insert at the Beginning:
1. Create a new node with the given data.
2. Set the `next` pointer of the new node to the current head.
3. If the list is not empty, update the `prev` pointer of the current head to the new node.
4. Update the head to point to the new node.

### Insert at the End:
1. Create a new node with the given data.
2. Traverse the list to find the last node.
3. Update the `next` pointer of the last node to the new node.
4. Update the `prev` pointer of the new node to the last node.

### Insert at a Specific Position:
1. Traverse the list to find the node at position `pos - 1`.
2. Create a new node with the given data.
3. Update the `next` pointer of the new node to the `next` pointer of the current node.
4. Update the `prev` pointer of the new node to the current node.
5. Update the pointers of the surrounding nodes to include the new node.

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

    // Insert at the beginning
    public void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        if (head != null) {
            newNode.next = head;
            head.prev = newNode;
        }
        head = newNode;
    }

    // Insert at the end
    public void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.next = newNode;
        newNode.prev = temp;
    }

    // Insert at a specific position
    public void insertAtPosition(int data, int position) {
        if (position <= 0) {
            System.out.println("Invalid position");
            return;
        }

        Node newNode = new Node(data);

        if (position == 1) {
            insertAtBeginning(data);
            return;
        }

        Node temp = head;
        for (int i = 1; i < position - 1; i++) {
            if (temp == null) {
                System.out.println("Position out of bounds");
                return;
            }
            temp = temp.next;
        }

        if (temp == null) {
            System.out.println("Position out of bounds");
            return;
        }

        newNode.next = temp.next;
        newNode.prev = temp;

        if (temp.next != null) {
            temp.next.prev = newNode;
        }
        temp.next = newNode;
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

        // Insert at the beginning
        dll.insertAtBeginning(10);
        dll.insertAtBeginning(5);
        System.out.println("After inserting at the beginning:");
        dll.printList(); // Output: 5 10

        // Insert at the end
        dll.insertAtEnd(20);
        dll.insertAtEnd(25);
        System.out.println("After inserting at the end:");
        dll.printList(); // Output: 5 10 20 25

        // Insert at a specific position
        dll.insertAtPosition(15, 3);
        System.out.println("After inserting at position 3:");
        dll.printList(); // Output: 5 10 15 20 25
    }
}
```
