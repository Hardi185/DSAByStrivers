Design an algorithm that collects daily price quotes for some stock and returns the span of that stock's price for the current day.


The span of the stock's price in one day is the maximum number of consecutive days (starting from that day and going backward) for which the stock price was less than or equal to the price of that day.

For example, if the prices of the stock in the last four days is [7,2,1,2] and the price of the stock today is 2, then the span of today is 4 because starting from today, the price of the stock was less than or equal 2 for 4 consecutive days.


Also, if the prices of the stock in the last four days is [7,34,1,2] and the price of the stock today is 8, then the span of today is 3 because starting from today, the price of the stock was less than or equal 8 for 3 consecutive days.

Implement the StockSpanner class:
StockSpanner() Initializes the object of the class.
int next(int price) Returns the span of the stock's price given that today's price is price.
 

```yaml
Example:
Input:
["StockSpanner", "next", "next", "next", "next", "next", "next", "next"]
[[], [100], [80], [60], [70], [60], [75], [85]]
Output:
[null, 1, 1, 1, 2, 1, 4, 6]

Explanation:
StockSpanner stockSpanner = new StockSpanner();
stockSpanner.next(100); // return 1
stockSpanner.next(80);  // return 1
stockSpanner.next(60);  // return 1
stockSpanner.next(70);  // return 2
stockSpanner.next(60);  // return 1
stockSpanner.next(75);  // return 4, because the last 4 prices (including today's price of 75) were less than or equal to today's price.
stockSpanner.next(85);  // return 6
```

---

## Breakdown of Calculations

### `next(100)`:
- `prices = [100]`
- No previous elements to compare, span = `1`
- **Output**: `1`

### `next(80)`:
- `prices = [100, 80]`
- 80 is smaller than 100, span = `1`
- **Output**: `1`

### `next(60)`:
- `prices = [100, 80, 60]`
- 60 is smaller than 80, span = `1`
- **Output**: `1`

### `next(70)`:
- `prices = [100, 80, 60, 70]`
- 70 > 60 → span increases to `2`
- **Output**: `2`

### `next(60)`:
- `prices = [100, 80, 60, 70, 60]`
- 60 is smaller than 70, span = `1`
- **Output**: `1`

### `next(75)`:
- `prices = [100, 80, 60, 70, 60, 75]`
- 75 > 60 → span = `2`
- 75 > 70 → span = `3`
- 75 > 60 → span = `4`
- **Output**: `4`

### `next(85)`:
- `prices = [100, 80, 60, 70, 60, 75, 85]`
- 85 > 75 → span = `2`
- 85 > 60 → span = `3`
- 85 > 70 → span = `4`
- 85 > 60 → span = `5`
- 85 > 80 → span = `6`
- **Output**: `6`

## Approach 1:
```java
import java.util.ArrayList;
import java.util.List;

class StockSpanner {
    private List<Integer> prices;

    // Initialize the StockSpanner object.
    public StockSpanner() {
        prices = new ArrayList<>();
    }

    // Returns the span of the stock's price for the current day.
    public int next(int price) {
        prices.add(price); // Add today's price to the list.
        int span = 1; // Initialize span as 1 (the current day itself).

        // Traverse backward to calculate the span.
        for (int i = prices.size() - 2; i >= 0; i--) {
            if (prices.get(i) <= price) {
                span++;
            } else {
                break;
            }
        }
        return span;
    }

    public static void main(String[] args) {
        StockSpanner stockSpanner = new StockSpanner();

        System.out.println(stockSpanner.next(100)); // Output: 1
        System.out.println(stockSpanner.next(80));  // Output: 1
        System.out.println(stockSpanner.next(60));  // Output: 1
        System.out.println(stockSpanner.next(70));  // Output: 2
        System.out.println(stockSpanner.next(60));  // Output: 1
        System.out.println(stockSpanner.next(75));  // Output: 4
        System.out.println(stockSpanner.next(85));  // Output: 6
    }
}
```

## Approach 2:
```java
import java.util.Stack;

class Pair {
    int price;
    int index;

    public Pair(int price, int index) {
        this.price = price;
        this.index = index;
    }
}

class StockSpanner {
    private Stack<Pair> stack;
    private int index;

    // Initialize the StockSpanner object.
    public StockSpanner() {
        stack = new Stack<>();
        index = -1; // Start index at -1 since we increment before usage.
    }

    // Returns the span of the stock's price for the current day.
    public int next(int price) {
        index++; // Increment index for the current day.

        // Remove elements from the stack that have prices less than or equal to the current price.
        while (!stack.isEmpty() && stack.peek().price <= price) {
            stack.pop();
        }

        // Calculate the span:
        int span = stack.isEmpty() ? index + 1 : index - stack.peek().index;

        // Push the current price and its index onto the stack.
        stack.push(new Pair(price, index));

        return span;
    }

    public static void main(String[] args) {
        StockSpanner stockSpanner = new StockSpanner();

        System.out.println(stockSpanner.next(100)); // Output: 1
        System.out.println(stockSpanner.next(80));  // Output: 1
        System.out.println(stockSpanner.next(60));  // Output: 1
        System.out.println(stockSpanner.next(70));  // Output: 2
        System.out.println(stockSpanner.next(60));  // Output: 1
        System.out.println(stockSpanner.next(75));  // Output: 4
        System.out.println(stockSpanner.next(85));  // Output: 6
    }
}
```
---

## Complexity comparision:

| **Metric**          | **Brute Force (Approach 1)**    | **Stack (Approach 2)**        |
|----------------------|----------------------------------|--------------------------------|
| **Time Complexity**  | \(O(n^2)\)                     | \(O(n)\)                      |
| **Space Complexity** | \(O(n)\)                       | \(O(n)\)                      |
| **Efficiency**       | Slower for large datasets      | Much faster for large datasets|

