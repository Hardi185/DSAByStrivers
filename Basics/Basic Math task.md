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

---

# 2. Palindrome

**Algorithm:**

- Reverse the number.
- Check if the reversed number equals the original number.
- If true, the number is a palindrome.

**Code:**

```java
public class PalindromeNumber {
    public static void main(String[] args) {
        int num = 121;
        if (isPalindrome(num)) {
            System.out.println(num + " is a palindrome.");
        } else {
            System.out.println(num + " is not a palindrome.");
        }
    }

    public static boolean isPalindrome(int num) {
        int original = num;
        int reversed = 0;
        while (num != 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }
        return original == reversed;
    }
}
```
**Output:** 
121 is a palindrome.

---

# 3. GCD or HCF

**Algorithm:**

- Use the Euclidean algorithm:
    - If b == 0, a is the GCD.
    - Else, compute gcd(b, a % b) recursively.

**Code:**

```java
public class GCDExample {
    public static void main(String[] args) {
        int a = 56, b = 98;
        int gcd = findGCD(a, b);
        System.out.println("GCD of " + a + " and " + b + ": " + gcd);
    }

    public static int findGCD(int a, int b) {
        if (b == 0) {
            return a;
        }
        return findGCD(b, a % b);
    }
}
```

**Output:** 
GCD of 56 and 98: 14

**Steps for input** `a = 56`, `b = 98`:

1. **Call** `findGCD(56, 98)`
   - Since `b != 0`, we call `findGCD(98, 56 % 98)` → `findGCD(98, 56)`

2. **Call** `findGCD(98, 56)`
   - Since `b != 0`, we call `findGCD(56, 98 % 56)` → `findGCD(56, 42)`

3. **Call** `findGCD(56, 42)`
   - Since `b != 0`, we call `findGCD(42, 56 % 42)` → `findGCD(42, 14)`

4. **Call** `findGCD(42, 14)`
   - Since `b != 0`, we call `findGCD(14, 42 % 14)` → `findGCD(14, 0)`

5. **Call** `findGCD(14, 0)`
   - Since `b == 0`, we return `a = 14`.

**Result:**
- The GCD of 56 and 98 is **14**.

---

# 4. Armstrong Number

**Algorithm:**
- For each digit, compute its cube (or power based on digit count).
- Sum up the cubes.
- If the sum equals the original number, it is an Armstrong number.

**Code:**

```java
public class ArmstrongNumber {
    public static void main(String[] args) {
        int num = 153;
        if (isArmstrong(num)) {
            System.out.println(num + " is an Armstrong number.");
        } else {
            System.out.println(num + " is not an Armstrong number.");
        }
    }

    public static boolean isArmstrong(int num) {
        int original = num, sum = 0;
        while (num != 0) {
            int digit = num % 10;
            sum += digit * digit * digit;
            num /= 10;
        }
        return sum == original;
    }
}
```

**Output:** 
153 is an Armstrong number.

**Steps for input** `num = 153`:

1. **Initialize** `original = 153`, `sum = 0`
   - `num = 153`

2. **First iteration:**
   - `digit = 153 % 10 = 3`
   - `sum = 0 + 3^3 = 27`
   - `num = 153 / 10 = 15`

3. **Second iteration:**
   - `digit = 15 % 10 = 5`
   - `sum = 27 + 5^3 = 27 + 125 = 152`
   - `num = 15 / 10 = 1`

4. **Third iteration:**
   - `digit = 1 % 10 = 1`
   - `sum = 152 + 1^3 = 153`
   - `num = 1 / 10 = 0`

5. **Stop** since `num = 0`.

**Result:**
- Since `sum = 153` and `original = 153`, **153 is an Armstrong number**.

---

# 5. Print All Divisors

**Algorithm:**

- Loop from 1 to the number.
- Check if the number is divisible by the loop variable.
- If true, print the divisor.

**Code:**

```java
public class Divisors {
    public static void main(String[] args) {
        int num = 28;
        System.out.println("Divisors of " + num + ":");
        printDivisors(num);
    }

    public static void printDivisors(int num) {
        for (int i = 1; i <= num; i++) {
            if (num % i == 0) {
                System.out.print(i + " ");
            }
        }
    }
}
```

**Output:**
Divisors of 28:
1 2 4 7 14 28

**Steps for input** `num = 28`:

1. **Loop from 1 to 28:**
   - For `i = 1`, `28 % 1 == 0`, so print `1`.
   - For `i = 2`, `28 % 2 == 0`, so print `2`.
   - For `i = 4`, `28 % 4 == 0`, so print `4`.
   - For `i = 7`, `28 % 7 == 0`, so print `7`.
   - For `i = 14`, `28 % 14 == 0`, so print `14`.
   - For `i = 28`, `28 % 28 == 0`, so print `28`.

**Result:**
- The divisors of `28` are: `1 2 4 7 14 28`.

---

# 6. Check Prime Number

**Algorithm:**

- Loop from 2 to the square root of the number.
    - If the number is divisible by any loop variable, it is not prime.
    - Otherwise, it is prime.

**Why Check Only Up to the Square Root?**

Example: Checking the divisors of `36`

The factors of `36` are:  
`1, 2, 3, 4, 6, 9, 12, 18, 36`

Notice that for each factor smaller than the square root (6), there is a corresponding factor larger than the square root. For instance:
- `1 * 36`
- `2 * 18`
- `3 * 12`
- `4 * 9`
- `6 * 6`

This means if a number `N` is divisible by any number larger than its square root, it will have already been "paired" with a factor smaller than the square root earlier in the process. Therefore, there's no need to check beyond the square root of `N` because we would be duplicating checks.


**Code:**

```java
public class PrimeCheck {
    public static void main(String[] args) {
        int num = 29;
        if (isPrime(num)) {
            System.out.println(num + " is a prime number.");
        } else {
            System.out.println(num + " is not a prime number.");
        }
    }

    public static boolean isPrime(int num) {
        if (num <= 1) return false;
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) return false;
        }
        return true;
    }
}
```

**Output:**
29 is a prime number.

**Steps for input** `num = 29`:

1. **Check if `num <= 1`:**
   - Since `29` is greater than `1`, proceed to the next step.

2. **Loop from `i = 2` to `sqrt(29) ≈ 5.39`:**
   - For `i = 2`, `29 % 2 != 0`, so continue.
   - For `i = 3`, `29 % 3 != 0`, so continue.
   - For `i = 4`, `29 % 4 != 0`, so continue.
   - For `i = 5`, `29 % 5 != 0`, so continue.

3. **Since no divisor was found, return `true`.**

**Result:**
- `29` is a prime number.
