# Patterns:

![image](https://github.com/user-attachments/assets/96e3b487-e49d-4265-903f-c73ba27b0026)

### Code:
```java
class Main {
   static void pattern1(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 0; i < N; i++)
    {
         // This is the inner loop which here, loops for the columns
        // as we have to print a rectangular pattern.
        for (int j = 0; j < N; j++)
        {
            System.out.print("* ");
        }

         // As soon as N stars are printed, we move to the
        // next row and give a line break otherwise all stars
        // would get printed in 1 line.
        System.out.println();
    }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern1(N);
    }
}
```

```yaml
* * * * *
* * * * *
* * * * *
* * * * *
* * * * *
```

---

![image](https://github.com/user-attachments/assets/628873a2-7bb7-4c1b-948a-c8628ce952ef)

### Code:
```java
class Main {
   static void pattern2(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 0; i < N; i++)
    {
         // This is the inner loop which loops for the columns
        // no. of columns = row number for each line here.
        for (int j = 0; j <= i; j++)
        {
            System.out.print("* ");
        }

         // As soon as stars for each iteration are printed, we move to the
        // next row and give a line break otherwise all stars
        // would get printed in 1 line.
        System.out.println();
    }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern2(N);
    }
}
```

```yaml
* 
* * 
* * * 
* * * * 
* * * * *
```

---

![image](https://github.com/user-attachments/assets/c3f7aa14-ec5e-471d-8de4-6b9c4b0b0e43)

### Code:
```java
class Main {
   static void pattern3(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 1; i <= N; i++)
    {
        // This is the inner loop which loops for the columns
       // no. of columns = row number for each line here.
       // Here, we print numbers from 1 to the row number
       // instead of stars in each row.
        for (int j = 1; j <= i; j++)
        {
            System.out.print(j+" ");
        }

         // As soon as numbers for each iteration are printed, we move to the
        // next row and give a line break otherwise all numbers
        // would get printed in 1 line.
        System.out.println();
    }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern3(N);
    }
}
```
```yaml
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```
