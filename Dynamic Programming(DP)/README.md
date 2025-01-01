# Dynamic Programming:

Dynamic Programming can be described as storing answers to various sub-problems to be used later whenever required to solve the main problem.

The two common dynamic programming approaches are:

- **Memoization:** Known as the “top-down” dynamic programming, usually the problem is solved in the direction of the main problem to the base cases.
- **Tabulation:** Known as the “bottom-up '' dynamic programming, usually the problem is solved in the direction of solving the base cases to the main problem

![image](https://github.com/user-attachments/assets/4d4a74fc-8a1d-4d4a-9583-79d480dd36b4)

---

## Memoization:

As every number is equal to the sum of the previous two terms, the recurrence relation can be written as:

![image](https://github.com/user-attachments/assets/c3e553d7-c271-449c-92a5-e4d5f2bee0e5)

The basic pseudo-code for the problem will be given as:

![image](https://github.com/user-attachments/assets/8a4352f9-a7c0-4e85-a779-ff62f4bf10a9)

If we draw the recursive tree for n=5, it will be:

![image](https://github.com/user-attachments/assets/70a5c18c-740f-4722-8cdc-d1b9600f8ccb)

If there are two recursive calls inside a function, the program will run the first call, finish its execution and then run the second call. Due to this reason, each and every call in the recursive tree will be executed. This gives the recursive code its exponential time complexity.
Can we improve on this? The answer is Yes!

![image](https://github.com/user-attachments/assets/f1af2aae-841e-41b3-9cd7-fbd784fee605)

We want to compute f(2) as the second call from f(4), but in the recursive tree we had already computed f(2) once (in the first recursive call of f(3) ) Similar is the case with f(3), therefore if we somehow store these values, the first time we calculated it then we can simply find its value in constant time whenever we need it. This technique is called Memoization. Here the cases marked in yellow are called overlapping sub-problems and we need to solve them only once during the code execution.

### Code:
```java
import java.util.*;
class TUF{
static int f(int n, int[] dp){
    if(n<=1) return n;
    
    if(dp[n]!= -1) return dp[n];
    return dp[n]= f(n-1,dp) + f(n-2,dp);
}


public static void main(String args[]) {

  int n=5;
  int dp[]=new int[n+1];
  Arrays.fill(dp,-1);
  System.out.println(f(n,dp));
  
}
}
```

**Time Complexity:** `O(N)`

**Space Complexity:** `O(N)`

---

## Tabulation:

### Algo:
1. Declare dp[] with n+1.
2. First initialize the base condition values, i.e i=0 and i=1 of the dp array as 0 and 1 respectively.
3. Set an iterative loop that traverses the array( from index 2 to n) and for every index set its value as dp[i-1] + dp[i-2].
   
### Code:
```java
import java.util.*;
class TUF{
public static void main(String args[]) {

  int n=5;
  int dp[]=new int[n+1];
  Arrays.fill(dp,-1);
  dp[0]= 0;
  dp[1]= 1;
  
  for(int i=2; i<=n; i++){
      dp[i] = dp[i-1]+ dp[i-2];
  }
  System.out.println(dp[n]);
  
  
}
}
```

**Time Complexity:** `O(N)`

**Space Complexity:** `O(N)`

---

## Space Optimization:

![image](https://github.com/user-attachments/assets/531eada8-af65-4423-a5d7-de8f6b76c339)

We can use variable to eliminate the use of Array.

### Code:
```java
import java.util.*;
class TUF{
public static void main(String args[]) {
 int n=5;
  
  int prev2 = 0;
  int prev = 1;
  
  for(int i=2; i<=n; i++){
      int cur_i = prev2+ prev;
      prev2 = prev;
      prev= cur_i;
  }
  System.out.println(prev);
  
  
}
}
```

**Time Complexity:** `O(N)`

**Space Complexity:** `O(1)`
