PROBLEM:
Given an array of integer arr. Your task is to construct the linked list from arr & return the head of the linked list.
Examples:

Input: arr = [1, 2, 3, 4, 5]
Output: LinkedList: 1->2->3->4->5
Explanation: Linked list for the given array will be

Input: arr = [2, 4, 6, 7, 5, 1, 0]
Output: LinkedList: 2->4->6->7->5->1->0
Explanation: Linked list for the given array will be

__________________________________________________________________________________________________________________________
CODE:
class ListNode {
    int val;
    ListNode next;

    ListNode(int val) {
        this.val = val;
        this.next = null;
    }
}

public class Solution {
    public static ListNode constructLinkedList(int[] arr) {
        if (arr.length == 0) {
            return null; // Return null if the array is empty
        }

        // Create the head of the linked list
        ListNode head = new ListNode(arr[0]);
        ListNode current = head;

        // Iterate through the array, starting from the second element
        for (int i = 1; i < arr.length; i++) {
            // Create a new node with the current array element
            ListNode newNode = new ListNode(arr[i]);
            // Link the new node to the current node
            current.next = newNode;
            // Move the current pointer to the new node
            current = newNode;
        }

        return head;
    }

    // Helper function to print the linked list
    public static void printLinkedList(ListNode head) {
        ListNode current = head;
        while (current != null) {
            System.out.print(current.val);
            if (current.next != null) {
                System.out.print("->");
            }
            current = current.next;
        }
        System.out.println();
    }

    public static void main(String[] args) {
        int[] arr1 = {1, 2, 3, 4, 5};
        ListNode head1 = constructLinkedList(arr1);
        System.out.print("LinkedList: ");
        printLinkedList(head1);

        int[] arr2 = {2, 4, 6, 7, 5, 1, 0};
        ListNode head2 = constructLinkedList(arr2);
        System.out.print("LinkedList: ");
        printLinkedList(head2);
    }
}
___________________________________________________________________________________________________________________________
BASICS OF LL:
-->A linked list is a linear data structure where elements, called nodes, are connected sequentially. 
Unlike arrays, linked lists do not store elements in contiguous memory locations. 
Instead, each node in a linked list contains:

Data: The actual value of the node.
Pointer/Reference (next): A link or reference to the next node in the sequence.
Types of Linked Lists

-->There are several types of linked lists, each with its own structure:
Singly Linked List: Each node has a reference to the next node only.
Doubly Linked List: Each node has two references: one to the next node and another to the previous node.
Circular Linked List: The last node points back to the first node, making a circular structure

CODE EXPLAINATION:

1)Node Definition: ListNode is a class representing each node in the linked list. Each node has a val (value) and a next (reference to the next node).
2)Constructing the Linked List:
Start by creating the head of the linked list using the first element in the array.
Loop through the remaining elements, create a new node for each, and link it to the previous node.
