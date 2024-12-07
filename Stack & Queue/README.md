# Stack and Queue in Java

Stack and Queue are both abstract data structures that allow the storage and retrieval of elements. They are both used to manage data in a certain order, but the order in which elements are retrieved differs. Let’s understand each data structure and see Java implementations.

## Stack

A **Stack** is a Last In, First Out (LIFO) data structure. This means that the last element added to the stack is the first one to be removed.

### Operations on Stack:
- **push()**: Adds an element to the top of the stack.
- **pop()**: Removes the element from the top of the stack.
- **peek()**: Returns the top element without removing it.
- **isEmpty()**: Checks if the stack is empty.

### Explanation:
- We create a `Stack<Integer>`.
- We add elements using `push()` and remove them using `pop()`.
- We check the top element using `peek()` and if the stack is empty using `isEmpty()`.

## Queue

A **Queue** is a First In, First Out (FIFO) data structure. This means that the first element added to the queue is the first one to be removed.

### Operations on Queue:
- **enqueue()**: Adds an element to the end of the queue.
- **dequeue()**: Removes the element from the front of the queue.
- **peek()**: Returns the front element without removing it.
- **isEmpty()**: Checks if the queue is empty.

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

