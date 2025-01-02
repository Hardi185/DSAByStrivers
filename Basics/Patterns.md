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

```yaml
A
A B
A B C
A B C D
A B C D E
```

### Code:
```java
class Main {
   
   static void pattern14(int N)
{
     
      // Outer loop for the number of rows.
      for(int i=0;i<N;i++){
          
          // Inner loop will loop for i times and
          // print alphabets from A to A + i.
          for(char ch = 'A'; ch<='A'+i;ch++){
              System.out.print(ch + " ");
              
          }
          // As soon as the letters for each iteration are printed, we move to the
          // next row and give a line break otherwise all letters
          // would get printed in 1 line.
          System.out.println();
         
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern14(N);
    }
}
```

---

```yaml
A B C D E F
A B C D E 
A B C D
A B C
A B
A
```

### Code:
```java
class Main {
   
   static void pattern15(int N)
{
     
      // Outer loop for the number of rows.
      for(int i=0;i<N;i++){
          
          // Inner loop will loop for i times and
          // print alphabets from A to A + (N-i-1).
          for(char ch = 'A'; ch<='A'+(N-i-1);ch++){
              System.out.print(ch + " ");
              
          }
          // As soon as the letters for each iteration are printed, we move to the
          // next row and give a line break otherwise all letters
          // would get printed in 1 line.
          System.out.println();
         
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern15(N);
    }
}
```

---

```yaml
A 
B B
C C C
D D D D
E E E E E
F F F F F F
```

### Code:
````java
class Main {
   
   static void pattern16(int N)
{
     
      // Outer loop for the number of rows.
      for(int i=0;i<N;i++){
          
          
          for(int j=0;j<=i;j++){
              
              // same char which is defined 
              // is to be printed i times in that row.
              System.out.print((char)((int)('A'+i)) + " ");
              
          }
          // As soon as the letters for each iteration are printed, we move to the
          // next row and give a line break otherwise all letters
          // would get printed in 1 line.
          System.out.println();
         
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern16(N);
    }
}
````

---

```yaml
     A     
    ABA    
   ABCBA   
  ABCDCBA  
 ABCDEDCBA 
ABCDEFEDCBA
```

### Code:
```java
class Main {
   
   static void pattern17(int N)
{
     
      // Outer loop for the number of rows.
      for(int i=0;i<N;i++){
          
          // for printing the spaces.
          for(int j=0;j<N-i-1;j++){
              System.out.print(" ");
          }
          
          // for printing the characters.
          char ch = 'A';
          int breakpoint = (2*i+1)/2;
          for(int j=1;j<=2*i+1;j++){
              
              System.out.print(ch);
              if(j <= breakpoint) ch++;
              else ch--;
          }
          
          // for printing the spaces again.
          for(int j=0;j<N-i-1;j++){
              System.out.print(" ");
          }
          // As soon as the letters for each iteration are printed, we move to the
          // next row and give a line break otherwise all letters
          // would get printed in 1 line.
          System.out.println();
          
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern17(N);
    }
}
```

---

```yaml
F
E F
D E F
C D E F
B C D E F
A B C D E F
```

### Code:
```java
class Main {
   
   static void pattern18(int N)
{
       // Outer loop for the no. of rows.
       for(int i=0;i<N;i++){
          
          // Inner loop for printing the alphabets from
          // A + N -1 -i (i is row no.) to A + N -1 ( E in this case).
          for(char ch =(char)(int)('A'+N-1-i);ch<=(char)(int)('A'+N-1);ch++){
              
              System.out.print(ch + " ");
          }
          
          // As soon as the letters for each iteration are printed, we move to the
          // next row and give a line break otherwise all letters
          // would get printed in 1 line.
          System.out.println();
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern18(N);
    }
}
```

---

![image](https://github.com/user-attachments/assets/af3c15d2-2f93-4eec-bf90-235aaef20b8e)

### Code:
```java
class Main {
   
   static void pattern19(int N)
{
      // for the upper half of the pattern.
      
      // initial spaces.
      int iniS = 0;
      for(int i=0;i< N;i++){
          
          //for printing the stars in the row.
          for(int j=1;j<=N-i;j++){
              System.out.print("*");
          }
          
          //for printing the spaces in the row.
          for(int j=0;j<iniS;j++){
              System.out.print(" ");
          }
          
          //for printing the stars in the row.
          for(int j=1;j<=N-i;j++){
              System.out.print("*");
          }
          
          // The spaces increase by 2 every time we hit a new row.
          iniS+=2;
          
          // As soon as the letters for each iteration are printed, we move to the
          // next row and give a line break otherwise all letters
          // would get printed in 1 line.
          System.out.println();
      }
      
      // for lower half of the pattern
      
      // initial spaces.
      iniS = 2*N -2;
      for(int i=1;i<=N;i++){
          
          //for printing the stars in the row.
          for(int j=1;j<=i;j++){
              System.out.print("*");
          }
          
          //for printing the spaces in the row.
          for(int j=0;j<iniS;j++){
              System.out.print(" ");
          }
          
          //for printing the stars in the row.
          for(int j=1;j<=i;j++){
              System.out.print("*");
          }
          
          // The spaces decrease by 2 every time we hit a new row.
          iniS-=2;
          
          // As soon as the letters for each iteration are printed, we move to the
          // next row and give a line break otherwise all letters
          // would get printed in 1 line.
          System.out.println();
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern19(N);
    }
}
```

---

![image](https://github.com/user-attachments/assets/3a1181e2-7e5c-4d6d-9d88-26c8d988eeeb)

### Code:
```java
class Main {
   
   static void pattern20(int n)
{
      // initialising the spaces.
      int spaces = 2*n-2;
      
      // Outer loop for printing row.
      for(int i = 1;i<=2*n-1;i++){
          
          // stars for first half
          int stars = i;
          
          // stars for the second half.
          if(i>n) stars = 2*n - i;
          
          //for printing the stars
          for(int j=1;j<=stars;j++){
              System.out.print("*");
          }
          
          //for printing the spaces
          for(int j = 1;j<=spaces;j++){
              System.out.print(" ");
          }
          
          //for printing the stars
          for(int j = 1;j<=stars;j++){
              System.out.print("*");
          }
          
          // As soon as the stars for each iteration are printed, we move to the
          // next row and give a line break otherwise all stars
          // would get printed in 1 line.
          System.out.println();
          if(i<n) spaces -=2;
          else spaces +=2;
      }
}

    public static void main(String[] args) {
        
        // Here, we have taken the value of N as 5.
        // We can also take input from the user.
        int N = 5;
        pattern20(N);
    }
}
```

---

```yaml
******
*    *
*    *
*    *
*    *
******
```

### Code:
```java
class Main {
   
   static void pattern21(int n)
{
      // outer loop for no. of rows.
     for(int i=0;i<n;i++){
         
         // inner loop for printing the stars at borders only.
         for(int j=0;j<n;j++){
             
             if(i==0 || j==0 || i==n-1 || j==n-1)
                System.out.print("*");
                
             // if not border index, print space.
             else System.out.print(" ");
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
        pattern21(N);
    }
}
```

---

```yaml
5 5 5 5 5 5 5 5 5 
5 4 4 4 4 4 4 4 5 
5 4 3 3 3 3 3 4 5 
5 4 3 2 2 2 3 4 5 
5 4 3 2 1 2 3 4 5 
5 4 3 2 2 2 3 4 5 
5 4 3 3 3 3 3 4 5 
5 4 4 4 4 4 4 4 5 
5 5 5 5 5 5 5 5 5
```

### Code:
```java
class Main {
   
   static void pattern22(int n)
{
      // Outer loop for no. of rows
      for(int i=0;i<2*n-1;i++){
         
         // inner loop for no. of columns.
         for(int j=0;j<2*n-1;j++){
             
             // Initialising the top, down, left and right indices of a cell.
             int top = i;
             int bottom = j;
             int right = (2*n - 2) - j;
             int left = (2*n - 2) - i;
             
             // Min of 4 directions and then we subtract from n
             // because previously we would get a pattern whose border
             // has 0's, but we want with border N's and then decrease inside.
             System.out.print(n- Math.min(Math.min(top,bottom), Math.min(left,right)) + " ");
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
        pattern22(N);
    }
}
```
