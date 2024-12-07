# Stack and Queue in Java

Stack and Queue are both abstract data structures that allow the storage and retrieval of elements. They are both used to manage data in a certain order, but the order in which elements are retrieved differs. Let’s understand each data structure and see Java implementations.

## Stack

![stack](https://github.com/user-attachments/assets/375a8bee-d318-4e6c-811a-671b794fa6e8)

A **Stack** is a Last In, First Out (LIFO) data structure. This means that the last element added to the stack is the first one to be removed.

### Operations on Stack:
- **push()**: Adds an element to the top of the stack.
- **pop()**: Removes the element from the top of the stack.
- **peek()**: Returns the top element without removing it.
- **isEmpty()**: Checks if the stack is empty.

### Stack Implementation in Java

```java
import java.util.Stack;

public class StackExample {

    public static void main(String[] args) {
        // Create a stack of integers
        Stack<Integer> stack = new Stack<>();

        // Pushing elements to the stack
        stack.push(10);
        stack.push(20);
        stack.push(30);
        stack.push(40);

        System.out.println("Top element (peek): " + stack.peek());  // Top element without removing it
        System.out.println("Is stack empty? " + stack.isEmpty());  // Check if the stack is empty

        // Popping elements from the stack
        System.out.println("Popped element: " + stack.pop());  // Removes 40
        System.out.println("Popped element: " + stack.pop());  // Removes 30

        // Print remaining elements in the stack
        System.out.println("Remaining stack: " + stack);

        // Popping all remaining elements
        while (!stack.isEmpty()) {
            System.out.println("Popped element: " + stack.pop());
        }

        // Check if the stack is empty
        System.out.println("Is stack empty? " + stack.isEmpty());
    }
}
```

**Output:**
```yaml
Top element (peek): 40
Is stack empty? false
Popped element: 40
Popped element: 30
Remaining stack: [10, 20]
Popped element: 20
Popped element: 10
Is stack empty? true
```

### Explanation:
- We create a `Stack<Integer>`.
- We add elements using `push()` and remove them using `pop()`.
- We check the top element using `peek()` and if the stack is empty using `isEmpty()`.

## Queue

![1_lbVhTEoFe6OKb8Xf83QSeg](https://github.com/user-attachments/assets/d48a00c2-9c12-4e0c-9b54-8fa6ad67ea5c)

A **Queue** is a First In, First Out (FIFO) data structure. This means that the first element added to the queue is the first one to be removed.

### Operations on Queue:
- **enqueue()**: Adds an element to the end of the queue.
- **dequeue()**: Removes the element from the front of the queue.
- **peek()**: Returns the front element without removing it.
- **isEmpty()**: Checks if the queue is empty.

### Queue Implementation in Java

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {

    public static void main(String[] args) {
        // Create a queue of integers using LinkedList
        Queue<Integer> queue = new LinkedList<>();

        // Enqueue elements to the queue
        queue.offer(10);
        queue.offer(20);
        queue.offer(30);
        queue.offer(40);

        System.out.println("Front element (peek): " + queue.peek());  // Front element without removing it
        System.out.println("Is queue empty? " + queue.isEmpty());  // Check if the queue is empty

        // Dequeue elements from the queue
        System.out.println("Dequeued element: " + queue.poll());  // Removes 10
        System.out.println("Dequeued element: " + queue.poll());  // Removes 20

        // Print remaining elements in the queue
        System.out.println("Remaining queue: " + queue);

        // Dequeue all remaining elements
        while (!queue.isEmpty()) {
            System.out.println("Dequeued element: " + queue.poll());
        }

        // Check if the queue is empty
        System.out.println("Is queue empty? " + queue.isEmpty());
    }
}
```

**Output:**
```yaml
Front element (peek): 10
Is queue empty? false
Dequeued element: 10
Dequeued element: 20
Remaining queue: [30, 40]
Dequeued element: 30
Dequeued element: 40
Is queue empty? true
```

### Explanation:
- We use `LinkedList` to implement the `Queue` interface.
- We add elements using `offer()`, remove them using `poll()`, and check the front element using `peek()`.
- We check if the queue is empty using `isEmpty()`.

## Key Differences Between Stack and Queue:

| Feature  | Stack                  | Queue                        |
|----------|------------------------|------------------------------|
| Order    | Last In, First Out (LIFO) | First In, First Out (FIFO)    |
| Operations | push(), pop(), peek()  | enqueue(), dequeue(), peek()  |
| Use Case | Function calls, Undo operations | Task scheduling, Breadth-First Search (BFS) |
| Example  | Web browser history (back button), Undo functionality | Print queue, Task scheduling in OS |

