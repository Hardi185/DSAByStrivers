# DSAByStrivers
A to Z DSA sheet

# Java Collections Cheat Sheet

This cheat sheet provides an overview of the main Java collection interfaces, their implementations, and common operations.

---

## 1. List (Ordered, Allows Duplicates)
### Implementations:
- **ArrayList**: Resizable array, fast random access.
- **LinkedList**: Doubly-linked list, faster insertion/deletion.
- **Vector**: Synchronized version of ArrayList.

### Common Operations:
```java
List<String> list = new ArrayList<>();
list.add("A");          // Add an element
list.add(1, "B");       // Add at specific index
list.remove("A");       // Remove by value
list.remove(1);         // Remove by index
list.get(1);            // Access element at index
list.set(1, "C");       // Update element at index
list.contains("B");     // Check if element exists
list.size();            // Get size of the list
list.clear();           // Remove all elements
```

---

## 2. Set (Unordered, No Duplicates)
### Implementations:
- **HashSet**: Fast access, no guaranteed order.
- **LinkedHashSet**: Maintains insertion order.
- **TreeSet**: Sorted set.

### Common Operations:
```java
Set<Integer> set = new HashSet<>();
set.add(1);            // Add element
set.add(2);            // Add element
set.remove(1);         // Remove element
set.contains(2);       // Check if element exists
set.size();            // Get size of the set
set.clear();           // Remove all elements
```

---

## 3. Map (Key-Value Pairs, Keys are Unique)
### Implementations:
- **HashMap**: Fast access, no guaranteed order.
- **LinkedHashMap**: Maintains insertion order.
- **TreeMap**: Sorted by keys.

### Common Operations:
```java
Map<Integer, String> map = new HashMap<>();
map.put(1, "One");       // Add key-value pair
map.put(2, "Two");       // Add key-value pair
map.get(1);              // Get value by key
map.remove(1);           // Remove key-value pair
map.containsKey(2);      // Check if key exists
map.containsValue("Two"); // Check if value exists
map.size();              // Get size of the map
map.clear();             // Remove all entries

// Get all keys
Set<Integer> keySet = map.keySet();
System.out.println("Keys: " + keySet);

// Get all values
Collection<String> valueSet = map.values();
System.out.println("Values: " + valueSet);
```

---

## 4. Queue (FIFO Order)
### Implementations:
- **LinkedList**: Doubly-linked list.
- **PriorityQueue**: Sorted based on priority.

### Common Operations:
```java
Queue<String> queue = new LinkedList<>();
queue.add("A");         // Add element (throws exception if full)
queue.offer("B");       // Add element (returns false if full)
queue.poll();           // Remove and return head (null if empty)
queue.remove();         // Remove head (throws exception if empty)
queue.peek();           // Retrieve head without removing (null if empty)
queue.element();        // Retrieve head (throws exception if empty)
queue.size();           // Get size of the queue
```

---

## 5. Stack (LIFO Order)
### Implementations:
- **Stack**: Legacy, synchronized.
- Recommended: Use **Deque** with **ArrayDeque** or **LinkedList**.

### Common Operations:
```java
// Using Stack
Stack<Integer> stack = new Stack<>();
stack.push(10);         // Push element onto stack
stack.pop();            // Remove and return top element
stack.peek();           // Retrieve top element without removing
stack.isEmpty();        // Check if stack is empty
stack.size();           // Get size of the stack

// Using Deque (Recommended)
Deque<Integer> stackDeque = new ArrayDeque<>();
stackDeque.push(10);    // Push element
stackDeque.pop();       // Remove and return top element
stackDeque.peek();      // Retrieve top element
```

---

## 6. Other Common Utility Methods (All Collections)
### Iterate Over Collection:
```java
// Using for-each loop
for (String item : list) {
    System.out.println(item);
}

// Using Iterator
Iterator<String> iterator = list.iterator();
while (iterator.hasNext()) {
    System.out.println(iterator.next());
}
```

### Sort a List:
```java
Collections.sort(list); // Natural order
list.sort(Comparator.reverseOrder()); // Custom order
```

### Convert Array to List:
```java
List<String> list = Arrays.asList("A", "B", "C");
```

### Convert List to Array:
```java
String[] array = list.toArray(new String[0]);
```

---

## Summary of Key Characteristics
| Collection | Ordered? | Duplicates Allowed? | Key-Value Pairs? | Common Uses                     |
|------------|----------|---------------------|------------------|----------------------------------|
| **List**   | Yes      | Yes                 | No               | Dynamic arrays, maintaining order |
| **Set**    | No       | No                  | No               | Unique elements, fast lookup     |
| **Map**    | No       | Keys: No, Values: Yes | Yes             | Key-value lookups               |
| **Queue**  | Yes (FIFO) | Yes               | No               | Processing tasks in order        |
| **Stack**  | Yes (LIFO) | Yes               | No               | Reverse-order processing         |

---

This cheat sheet covers the essentials of Java collections, their implementations, and the most common operations. Let me know if you’d like more details on any specific part!

