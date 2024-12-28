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

Explanation
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
---

## Complexity comparision:
