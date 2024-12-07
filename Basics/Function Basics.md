#What is a Function:

A **function** is a block of reusable code that performs a specific task. Functions allow you to break down your program into smaller, manageable pieces. They promote modularity, reusability, and better organization of code.

---

## Pass by Value
### Definition:
When a function is called with arguments, a **copy of the argument's value** is passed to the function. Any changes made to the parameter inside the function **do not affect the original value** in the caller's scope.

### Characteristics:
- The original variable remains **unchanged**.
- More memory is used because a **copy** of the value is created.

### Example:
```cpp
#include <iostream>
using namespace std;

void modifyValue(int x) {  // Function receives a copy of the argument
    x = 10; // Modifies the local copy
}

int main() {
    int num = 5; // Original value
    modifyValue(num); // Pass by value
    cout << "Value of num: " << num << endl; // Output: 5
    return 0;
}
```
