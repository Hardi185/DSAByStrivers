# 1. Reverse Number

**Algorithm:**
- Initialize a variable reversed to 0.
- Extract the last digit using num % 10.
- Add it to reversed after multiplying it by 10.
- Remove the last digit from the number by num /= 10.
- Repeat until the number becomes 0.

**Code:**

```java
public class ReverseNumber {
    public static void main(String[] args) {
        int num = 12345;
        int reversed = reverseNumber(num);
        System.out.println("Reversed number: " + reversed);
    }

    public static int reverseNumber(int num) {
        int reversed = 0;
        while (num != 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }
        return reversed;
    }
}
```

**Output:** Reversed number: 54321
