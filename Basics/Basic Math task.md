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

**Steps for input `num = 12345`:**

1. **Initialize** `reversed = 0`
   - `num = 12345`

2. **First iteration**:
   - `digit = 12345 % 10 = 5`
   - `reversed = 0 * 10 + 5 = 5`
   - `num = 12345 / 10 = 1234`

3. **Second iteration**:
   - `digit = 1234 % 10 = 4`
   - `reversed = 5 * 10 + 4 = 54`
   - `num = 1234 / 10 = 123`

4. **Third iteration**:
   - `digit = 123 % 10 = 3`
   - `reversed = 54 * 10 + 3 = 543`
   - `num = 123 / 10 = 12`

5. **Fourth iteration**:
   - `digit = 12 % 10 = 2`
   - `reversed = 543 * 10 + 2 = 5432`
   - `num = 12 / 10 = 1`

6. **Fifth iteration**:
   - `digit = 1 % 10 = 1`
   - `reversed = 5432 * 10 + 1 = 54321`
   - `num = 1 / 10 = 0`

7. **Stop** since `num = 0`.

**Final reversed number:** `54321`
