# What is a Function:

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

---

## Pass by Reference in C++

### Definition:
When a function is called with arguments using references, the **function is given a reference (address)** to the argument. This means that any changes made to the parameter inside the function **directly affect the original variable** in the caller's scope.


### Characteristics:
- **No copy** of the variable is created, which saves memory.
- Changes made to the parameter inside the function **reflect in the original variable**.
- Enables efficient manipulation of large data structures or objects.


### Example:
```cpp
#include <iostream>
using namespace std;

void modifyReference(int &x) {  // Function receives a reference to the argument
    x = 10; // Modifies the original variable
}

int main() {
    int num = 5; // Original value
    modifyReference(num); // Pass by reference
    cout << "Value of num: " << num << endl; // Output: 10
    return 0;
}
```

## Key Differences:
| **Aspect**           | **Pass by Value**                 | **Pass by Reference**           |
|----------------------|-----------------------------------|----------------------------------|
| **Memory Usage**     | Copies the value, uses more memory | Uses the same memory as the original variable |
| **Effect on Original**| Original remains unchanged         | Original variable may be changed |
| **Speed**            | Slower due to copying             | Faster, no copying involved      |
