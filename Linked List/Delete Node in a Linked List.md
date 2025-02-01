# Delete a Node from a Singly Linked List

## Problem Statement
Given the head of a Singly Linked List, delete a node either from the head, the tail, or a specific position in the list, and return the modified linked list.

### Examples:

#### Example 1:
**Input:** 
LinkedList: `1->2->3->4->5`, delete from head

**Output:** 
`2->3->4->5`

**Explanation:** 
The node at the head of the linked list is deleted.

---

#### Example 2:
**Input:** 
LinkedList: `1->2->3->4->5`, delete from tail

**Output:** 
`1->2->3->4`

**Explanation:** 
The node at the tail of the linked list is deleted.

---

#### Example 3:
**Input:** 
LinkedList: `1->2->3->4->5`, delete at position 3 (1-indexed)

**Output:** 
`1->2->4->5`

**Explanation:** 
The node at position 3 is deleted.

---

## Approach

### Deleting a Node from the Head:
1. Update the head to the next node of the current head.
2. Return the updated head of the linked list.

### Deleting a Node from the Tail:
1. Traverse the list until the second last node.
2. Set the `next` pointer of the second last node to `null`.
3. Return the updated head of the linked list.

### Deleting a Node from a Specific Position:
1. Traverse the list to the node just before the specified position.
2. Update its `next` pointer to skip the node at the specified position.
3. Return the updated head of the linked list.

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
    // Method to delete a node from the head
    public static Node deleteFromHead(Node head) {
        if (head == null) return null;
        return head.next;
    }

    // Method to delete a node from the tail
    public static Node deleteFromTail(Node head) {
        if (head == null || head.next == null) return null;

        Node current = head;
        while (current.next.next != null) {
            current = current.next;
        }
        current.next = null;
        return head;
    }

    // Method to delete a node from a specific position (node 3)
    public static Node deleteFromPosition(Node node) {
        if (node == null || node.next == null) {
            return null;
        }

        node.val = node.next.val;  // Copy next node’s value into current node
        node.next = node.next.next;  // Remove the next node by skipping it
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
        // Example List: 1->2->3->4->5
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = new Node(4);
        head.next.next.next.next = new Node(5);

        // Delete from head
        System.out.print("After deleting from head: ");
        head = deleteFromHead(head);
        printList(head);

        // Delete from tail
        System.out.print("After deleting from tail: ");
        head = deleteFromTail(head);
        printList(head);

        // Delete from position 3
        System.out.print("After deleting from position 3: ");
        head = deleteFromPosition(head, 3);
        printList(head);
    }
}
```

### Initial Linked List(Remove at any position):
```
head -> [4] -> [5] -> [1] -> [9] -> null
```
We are given a reference to the node with value `5` (i.e., `node = head.next`).

### Steps to Delete Node:
1. **Copy Next Node's Value:**
   - Assign `node.val = node.next.val` to copy the value of the next node into the current node.

   **Before:**
   ```
   node -> [5] -> [1] -> [9] -> null
   ```
   **After:**
   ```
   node -> [1] -> [1] -> [9] -> null
   ```

2. **Skip Next Node:**
   - Assign `node.next = node.next.next` to remove the next node.

   **Before:**
   ```
   node -> [1] -> [1] -> [9] -> null
   ```
   **After:**
   ```
   node -> [1] -> [9] -> null
   ```

### Final Linked List:
```
head -> [4] -> [1] -> [9] -> null
```

---

## Explanation

### Steps to Delete a Node:
1. **Deleting from Head:**
   The head is updated to the next node.

2. **Deleting from Tail:**
   Traverse to the second last node and set its `next` pointer to `null`.

3. **Deleting from Position:**
   add next node's value to current and next node's reference to current, so copying next and that's how next node will be replced

---

## Complexity Analysis

### Time Complexity:
- **Deleting from Head:** O(1)
- **Deleting from Tail:** O(n)
- **Deleting from Position:** O(1) (in the worst case)

### Space Complexity:
- **O(1):** No extra space is used.

---



**Example 3:**
```
After deleting from position 3: 2->3->5->null
```

---
