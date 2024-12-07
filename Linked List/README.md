# Linked List Explained

A **Linked List** is a linear data structure where elements (called nodes) are stored in a sequence, and each node points to the next node in the list. Unlike arrays, linked lists do not require contiguous memory locations. Linked lists are dynamic and allow efficient insertion and deletion of elements.

## Types of Linked Lists:

1. **Singly Linked List (SLL)**: 
   - Each node contains **data** and a reference (or pointer) to the next node.

![Traversal-of-Singly-Linked-List](https://github.com/user-attachments/assets/f03b69de-3cbf-4ace-b136-192ca34d2d59)

2. **Doubly Linked List (DLL)**:
   - Each node contains **data**, a reference to the next node, and a reference to the previous node.

![ezgif com-gif-maker1](https://github.com/user-attachments/assets/752e7015-b6c1-44cb-9768-1b728e420c2a)

3. **Circular Linked List**:
   - The last node points back to the first node, forming a circle.

## Singly Linked List (SLL)

In a Singly Linked List, each node contains:

- **Data**: The actual data stored in the node.
- **Next**: A reference to the next node in the list.

### Singly Linked List Code in Java

```java
class SinglyLinkedList {

    // Node class represents an element in the linked list
    class Node {
        int data;
        Node next;

        public Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    // Head node of the linked list
    private Node head;

    // Constructor
    public SinglyLinkedList() {
        head = null;
    }

    // Add a node at the end of the list
    public void addNode(int data) {
        Node newNode = new Node(data);

        if (head == null) {
            head = newNode;  // If the list is empty, new node becomes the head
        } else {
            Node temp = head;
            while (temp.next != null) {
                temp = temp.next;  // Traverse till the last node
            }
            temp.next = newNode;  // Link the last node to the new node
        }
    }

    // Print the linked list
    public void printList() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " -> ");
            temp = temp.next;
        }
        System.out.println("null");
    }

    public static void main(String[] args) {
        SinglyLinkedList list = new SinglyLinkedList();

        // Adding nodes
        list.addNode(10);
        list.addNode(20);
        list.addNode(30);
        list.addNode(40);

        // Print the list
        list.printList();
    }
}
```

**Output:**
```yaml
10 -> 20 -> 30 -> 40 -> null
```

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

### Doubly Linked List Code in Java

```java
class DoublyLinkedList {

    // Node class represents an element in the doubly linked list
    class Node {
        int data;
        Node next;
        Node prev;

        public Node(int data) {
            this.data = data;
            this.next = null;
            this.prev = null;
        }
    }

    // Head node of the doubly linked list
    private Node head;

    // Constructor
    public DoublyLinkedList() {
        head = null;
    }

    // Add a node at the end of the list
    public void addNode(int data) {
        Node newNode = new Node(data);

        if (head == null) {
            head = newNode;  // If the list is empty, new node becomes the head
        } else {
            Node temp = head;
            while (temp.next != null) {
                temp = temp.next;  // Traverse till the last node
            }
            temp.next = newNode;  // Link the last node to the new node
            newNode.prev = temp;   // Link the new node back to the last node
        }
    }

    // Print the doubly linked list in forward direction
    public void printForward() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " <-> ");
            temp = temp.next;
        }
        System.out.println("null");
    }

    // Print the doubly linked list in backward direction
    public void printBackward() {
        if (head == null) return;  // If the list is empty, do nothing
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;  // Traverse to the last node
        }

        // Traverse backward from the last node
        while (temp != null) {
            System.out.print(temp.data + " <-> ");
            temp = temp.prev;
        }
        System.out.println("null");
    }

    public static void main(String[] args) {
        DoublyLinkedList list = new DoublyLinkedList();

        // Adding nodes
        list.addNode(10);
        list.addNode(20);
        list.addNode(30);
        list.addNode(40);

        // Print the list forward
        list.printForward();

        // Print the list backward
        list.printBackward();
    }
}
```

**Output:**

```yaml
10 <-> 20 <-> 30 <-> 40 <-> null
40 <-> 30 <-> 20 <-> 10 <-> null
```

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

