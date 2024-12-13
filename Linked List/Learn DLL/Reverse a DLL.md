# Reversing a Doubly Linked List in Java

This repository demonstrates two approaches to reverse a **Doubly Linked List (DLL)** in Java. Each approach is implemented with detailed explanations and comparisons.

## Approaches

### 1. Reverse Using a Stack
This approach uses an external data structure (a stack) to reverse the DLL.

#### Algorithm
1. Traverse the DLL and push each node onto a stack.
2. Pop nodes from the stack one by one and reconstruct the DLL in reverse order.
3. Update the head of the DLL to the last popped node.

#### Code
```java
import java.util.Stack;

class Node {
    int data;
    Node prev, next;

    Node(int data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}

class DoublyLinkedList {
    Node head;

    // Reverse using stack
    public void reverseUsingStack() {
        if (head == null) return;

        Stack<Node> stack = new Stack<>();
        Node temp = head;

        // Push all nodes onto the stack
        while (temp != null) {
            stack.push(temp);
            temp = temp.next;
        }

        // Reconstruct the DLL by popping nodes
        head = stack.pop();
        temp = head;
        while (!stack.isEmpty()) {
            Node poppedNode = stack.pop();
            temp.next = poppedNode;
            poppedNode.prev = temp;
            temp = poppedNode;
        }
        temp.next = null; // End the list
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
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;

        System.out.println("Original List:");
        dll.printList(); // Output: 1 2 3

        dll.reverseUsingStack();

        System.out.println("Reversed List (Using Stack):");
        dll.printList(); // Output: 3 2 1
    }
}
```

### 2. Reverse In-Place
This approach modifies the pointers of the DLL directly to reverse it.

#### Algorithm
1. Traverse the DLL and swap the `next` and `prev` pointers for each node.
2. Update the head of the DLL to the last node traversed.

#### Code
```java
class DoublyLinkedListInPlace {
    Node head;

    // Reverse in-place
    public void reverseInPlace() {
        if (head == null) return;

        Node temp = null;
        Node current = head;

        // Traverse and swap next and prev pointers
        while (current != null) {
            temp = current.prev;
            current.prev = current.next;
            current.next = temp;
            current = current.prev; // Move to the next node (prev due to reversal)
        }

        // Update head to the last node (new head)
        if (temp != null) {
            head = temp.prev;
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

public class MainInPlace {
    public static void main(String[] args) {
        DoublyLinkedListInPlace dll = new DoublyLinkedListInPlace();
        dll.head = new Node(1);
        dll.head.next = new Node(2);
        dll.head.next.prev = dll.head;
        dll.head.next.next = new Node(3);
        dll.head.next.next.prev = dll.head.next;

        System.out.println("Original List:");
        dll.printList(); // Output: 1 2 3

        dll.reverseInPlace();

        System.out.println("Reversed List (In-Place):");
        dll.printList(); // Output: 3 2 1
    }
}
```

## Complexity Comparison
| Approach        | Time Complexity | Space Complexity |
|------------------|-----------------|------------------|
| Using Stack      | O(n)            | O(n)             |
| In-Place Reversal | O(n)            | O(1)             |

## Explanation
1. **Using Stack**:
   - Requires additional space to store nodes in a stack.
   - Easy to implement but not space-efficient.

2. **In-Place Reversal**:
   - Directly modifies the pointers in the DLL.
   - Space-efficient as it uses only constant space.
