# Patterns:

```yaml
* * * * *
* * * * *
* * * * *
* * * * *
* * * * *
```

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

---

```yaml
* 
* * 
* * * 
* * * * 
* * * * *
```

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

---

```yaml
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

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

---

```yaml
1
2 2
3 3 3
4 4 4 4
5 5 5 5 5 
```

### Code:
```java
class Main {
   static void pattern4(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 1; i <= N; i++)
    {
        // This is the inner loop which loops for the columns
       // no. of columns = row number for each line here.
       // Here, we print numbers equal to the row number
       // instead of stars in each row.
        for (int j = 1; j <= i; j++)
        {
            System.out.print(i+" ");
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
        pattern4(N);
    }
}
```

---

````yaml
* * * * *
* * * * 
* * * 
* * 
* 
````

### Code:
```java
class Main {
   static void pattern5(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 0; i < N; i++)
    {
        // This is the inner loop which loops for the columns
       // no. of columns = (N - row index) for each line here.
        for (int j = N; j > i; j--)
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
        pattern5(N);
    }
}
```

---

```yaml
1 2 3 4 5
1 2 3 4
1 2 3
1 2 
1
```

### Code:
```java
class Main {
   static void pattern6(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 0; i < N; i++)
    {
        // This is the inner loop which loops for the columns
        // no. of columns = (N - row index) for each line here
        // as we have to print an inverted pyramid.
        // (N-j) will give us the numbers in a row starting from 1 to N-i.
        for (int j = N; j > i; j--)
        {
            System.out.print(N-j+1+" ");
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
        pattern6(N);
    }
}
```

---

```yaml
     *     
    ***    
   *****   
  *******  
 ********* 
***********
```

### Code:
```java
class Main {
   static void pattern7(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 0; i < N; i++)
    {
        // For printing the spaces before stars in each row
        for (int j =0; j<N-i-1; j++)
        {
            System.out.print(" ");
        }
       
        // For printing the stars in each row
        for(int j=0;j< 2*i+1;j++){
            
            System.out.print("*");
        }
        
        // For printing the spaces after the stars in each row
         for (int j =0; j<N-i-1; j++)
        {
            System.out.print(" ");
        }
       

        // As soon as the stars for each iteration are printed, we move to the
        // next row and give a line break otherwise all stars
        // would get printed in 1 line.
        System.out.println();
    }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern7(N);
    }
}
```

---

```yaml
***********
 *********
  *******
   ***** 
    ***    
     *
```

### Code:
```java
class Main {
   static void pattern8(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 0; i < N; i++)
    {
        // For printing the spaces before stars in each row
        for (int j =0; j<i; j++)
        {
            System.out.print(" ");
        }
       
        // For printing the stars in each row
        for(int j=0;j< 2*N -(2*i +1);j++){
            
            System.out.print("*");
        }
        
        // For printing the spaces after the stars in each row
        for (int j =0; j<i; j++)
        {
            System.out.print(" ");
        }
       

        // As soon as the stars for each iteration are printed, we move to the
        // next row and give a line break otherwise all stars
        // would get printed in 1 line.
        System.out.println();
    }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern8(N);
    }
}
```

---

```yaml
     *
    ***
   ***** 
  *******
 *********
***********  
***********
 *********
  *******
   ***** 
    ***    
     *
```

### Code:
```java
class Main {
   
   static void erect_pyramid(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 0; i < N; i++)
    {
        // For printing the spaces before stars in each row
        for (int j =0; j<N-i-1; j++)
        {
            System.out.print(" ");
        }
       
        // For printing the stars in each row
        for(int j=0;j< 2*i+1;j++){
            
            System.out.print("*");
        }
        
        // For printing the spaces after the stars in each row
         for (int j =0; j<N-i-1; j++)
        {
            System.out.print(" ");
        }
       

        // As soon as the stars for each iteration are printed, we move to the
        // next row and give a line break otherwise all stars
        // would get printed in 1 line.
        System.out.println();
    }
}

   static void inverted_pyramid(int N)
{
    // This is the outer loop which will loop for the rows.
    for (int i = 0; i < N; i++)
    {
        // For printing the spaces before stars in each row
        for (int j =0; j<i; j++)
        {
            System.out.print(" ");
        }
       
        // For printing the stars in each row
        for(int j=0;j< 2*N -(2*i +1);j++){
            
            System.out.print("*");
        }
        
        // For printing the spaces after the stars in each row
        for (int j =0; j<i; j++)
        {
            System.out.print(" ");
        }
       

        // As soon as the stars for each iteration are printed, we move to the
        // next row and give a line break otherwise all stars
        // would get printed in 1 line.
        System.out.println();
    }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        erect_pyramid(N);
        inverted_pyramid(N);
    }
}
```

---

```yaml
     *
     **
     *** 
     ****
     *****
     ******  
     *****
     ****
     ***    
     **
     *
```

### Code:
```java
class Main {
   
   static void pattern10(int N)
{
    // Outer loop for number of rows.
    for(int i=1;i<=2*N-1;i++){
        
          // stars would be equal to the row no. uptill first half
          int stars = i;
          
          // for the second half of the rotated triangle.
          if(i>N) stars = 2*N-i;
          
          // for printing the stars in each row.
          for(int j=1;j<=stars;j++){
              System.out.print("*");
          }
          
          // As soon as the stars for each iteration are printed, we move to the
          // next row and give a line break otherwise all stars
          // would get printed in 1 line.
          System.out.println();
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern10(N);
    }
}
```

**NOTE:** 2 different loops can also be used for inverted.

---

```yaml
1
01
101
0101
10101
```

### Code:
```java
class Main {
   
   static void pattern11(int N)
{
     // First row starts by printing a single 1.
      int start =1;
      
      // Outer loop for the no. of rows
      for(int i=0;i<N;i++){
          
          // if the row index is even then 1 is printed first
          // in that row.
          if(i%2 ==0) start = 1;
          
          // if odd, then the first 0 will be printed in that row.
          else start = 0;
          
          // We alternatively print 1's and 0's in each row by using
          // the inner for loop.
          for(int j=0;j<=i;j++){
              System.out.print(start);
              start = 1-start;
          }
      
      
        // As soon as the numbers for each iteration are printed, we move to the
        // next row and give a line break otherwise all numbers
        // would get printed in 1 line.
        System.out.println();
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern11(N);
    }
}
```

---

```yaml
1          1
12        21
123       321
1234    4321
12345  54321
123456654321
```

### Code:
```java
class Main {
   
   static void pattern12(int N)
{
     // initial no. of spaces in row 1.
     int spaces = 2*(N-1);
     
      // Outer loop for the number of rows.
      for(int i=1;i<=N;i++){
          
          // for printing numbers in each row
          for(int j=1;j<=i;j++){
          System.out.print(j);
          }
          
          // for printing spaces in each row
          for(int j = 1;j<=spaces;j++){
          System.out.print(" ");
          }
          
          // for printing numbers in each row
          for(int j=i;j>=1;j--){
           System.out.print(j);
          }
          
          // As soon as the numbers for each iteration are printed, we move to the
          // next row and give a line break otherwise all numbers
          // would get printed in 1 line.
          System.out.println();
          
          // After each iteration nos. increase by 2, thus
          // spaces will decrement by 2.
          spaces-=2;
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern12(N);
    }
}
```

---

```yaml
1
2  3
4  5  6
7  8  9  10
11  12  13  14  15
```

### Code:
```java
class Main {
   
   static void pattern13(int N)
{
     // starting number.
     int num =1;
      
      // Outer loop for the number of rows.
      for(int i=1;i<=N;i++){
          
          // Inner loop will loop for i times and
          // print numbers increasing by 1 each time.
          for(int j=1;j<=i;j++){
              System.out.print(num + " ");
              num =num+1;
          }
          // As soon as the numbers for each iteration are printed, we move to the
          // next row and give a line break otherwise all numbers
          // would get printed in 1 line.
          System.out.println();
         
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern13(N);
    }
}
```

---

