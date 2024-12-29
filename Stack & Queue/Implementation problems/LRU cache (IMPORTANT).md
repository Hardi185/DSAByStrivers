# LRU Cache

Design a data structure that follows the constraints of a Least Recently Used (LRU) cache.

### Implement the LRUCache class:
- LRUCache(int capacity) Initialize the LRU cache with positive size capacity.
- int get(int key) Return the value of the key if the key exists, otherwise return -1.
- void put(int key, int value) Update the value of the key if the key exists. Otherwise, add the key-value pair to the cache.
- If the number of keys exceeds the capacity from this operation, evict the least recently used key.
- The functions get and put must each run in O(1) average time complexity.

 
```yaml
Example:

Input:
["LRUCache", "put", "put", "get", "put", "get", "put", "get", "get", "get"]
[[2], [1, 1], [2, 2], [1], [3, 3], [2], [4, 4], [1], [3], [4]]
Output:
[null, null, null, 1, null, -1, null, -1, 3, 4]

Explanation:
LRUCache lRUCache = new LRUCache(2);
lRUCache.put(1, 1); // cache is {1=1}
lRUCache.put(2, 2); // cache is {1=1, 2=2}
lRUCache.get(1);    // return 1
lRUCache.put(3, 3); // LRU key was 2, evicts key 2, cache is {1=1, 3=3}
lRUCache.get(2);    // returns -1 (not found)
lRUCache.put(4, 4); // LRU key was 1, evicts key 1, cache is {4=4, 3=3}
lRUCache.get(1);    // return -1 (not found)
lRUCache.get(3);    // return 3
lRUCache.get(4);    // return 4
```

---

## Code:
```java
import java.util.*;

class LRUCache {
    // Node class for Doubly Linked List
    class Node {
        int key, value;
        Node prev, next;

        Node(int key, int value) {
            this.key = key;
            this.value = value;
        }
    }

    private final int capacity;
    private final Map<Integer, Node> cache;
    private final Node head, tail; // Dummy head and tail for DLL

    public LRUCache(int capacity) {
        this.capacity = capacity;
        cache = new HashMap<>();
        head = new Node(-1, -1); // Dummy head
        tail = new Node(-1, -1); // Dummy tail
        head.next = tail;
        tail.prev = head;
    }

    // Get the value of the key if it exists, otherwise return -1
    public int get(int key) {
        if (!cache.containsKey(key)) {
            return -1;
        }
        Node node = cache.get(key);
        moveToHead(node); // Update access order
        return node.value;
    }

    // Add or update the value of a key
    public void put(int key, int value) {
        if (cache.containsKey(key)) {
            Node node = cache.get(key);
            node.value = value; // Update the value
            moveToHead(node);   // Update access order
        } else {
            if (cache.size() == capacity) {
                removeLRU(); // Evict least recently used item
            }
            Node newNode = new Node(key, value);
            cache.put(key, newNode);
            addToHead(newNode);
        }
    }

    // Move a node to the head of the DLL
    private void moveToHead(Node node) {
        removeNode(node);
        addToHead(node);
    }

    // Add a node to the head of the DLL
    private void addToHead(Node node) {
        node.next = head.next;
        head.next.prev = node;
        head.next = node;
        node.prev = head;
    }

    // Remove a node from the DLL
    private void removeNode(Node node) {
        node.prev.next = node.next;
        node.next.prev = node.prev;
    }

    // Remove the least recently used item
    private void removeLRU() {
        Node lru = tail.prev;
        removeNode(lru);
        cache.remove(lru.key);
    }

    public static void main(String[] args) {
        LRUCache lRUCache = new LRUCache(2);

        lRUCache.put(1, 1); // cache is {1=1}
        lRUCache.put(2, 2); // cache is {1=1, 2=2}
        System.out.println(lRUCache.get(1)); // return 1
        lRUCache.put(3, 3); // LRU key was 2, evicts key 2, cache is {1=1, 3=3}
        System.out.println(lRUCache.get(2)); // returns -1 (not found)
        lRUCache.put(4, 4); // LRU key was 1, evicts key 1, cache is {4=4, 3=3}
        System.out.println(lRUCache.get(1)); // return -1 (not found)
        System.out.println(lRUCache.get(3)); // return 3
        System.out.println(lRUCache.get(4)); // return 4
    }
}
```

| **Metric**           | **Explanation**                                         | **Value**     |
|-----------------------|---------------------------------------------------------|---------------|
| **Time Complexity**   | - `get` and `put` use HashMap (O(1)) and DLL (O(1)) for constant time operations.<br>- Total: O(1) per operation (average). | **O(1)**      |
| **Space Complexity**  | - HashMap stores up to `capacity` items.<br>- DLL stores `capacity` items.<br>- Total: O(capacity). | **O(capacity)** |

---
