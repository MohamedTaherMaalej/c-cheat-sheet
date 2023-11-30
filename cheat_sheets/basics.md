# C Basics Cheat Sheet

## Data Types

### Primitive Data Types

- `int`: Integer type, e.g., `int x = 5;`
- `float`: Single-precision floating-point type, e.g., `float pi = 3.14;`
- `double`: Double-precision floating-point type, e.g., `double price = 19.99;`
- `char`: Character type, e.g., `char grade = 'A';`
- `void`: Represents absence of type, often used in function return types.

### Derived Data Types

- Arrays: Ordered collection of elements of the same type, e.g., `int numbers[5];`
- Pointers: Variables that store memory addresses, e.g., `int *ptr = &x;`
- Structures: User-defined composite data types, e.g.,

  ```c
  struct Point {
      int x;
      int y;
  };
  ```

## Variables and Constants

### Variables

Declare and initialize variables:

```c
int age;          // Declaration
age = 25;         // Initialization
```

Shortcut for declaration and initialization:

```c
int count = 0;    // Declaration and initialization
```

### Constants

Use the `const` keyword to define constants:

```c
const double PI = 3.14159;
```

## Control Structures

### Conditional Statements

#### `if` Statement

```c
if (condition) {
    // Code to execute if the condition is true
} else {
    // Code to execute if the condition is false
}
```

#### `switch` Statement

```c
switch (expression) {
    case constant1:
        // Code if expression equals constant1
        break;
    case constant2:
        // Code if expression equals constant2
        break;
    // ...
    default:
        // Code if expression doesn't match any constant
}
```

### Loops

#### `for` Loop

```c
for (int i = 0; i < 5; i++) {
    // Code to repeat
}
```

#### `while` Loop

```c
while (condition) {
    // Code to repeat while the condition is true
}
```

#### `do-while` Loop

```c
do {
    // Code to repeat at least once
} while (condition);
```

## Functions

### Function Declaration

```c
// Function declaration
int add(int a, int b);
```

### Function Definition

```c
// Function definition
int add(int a, int b) {
    return a + b;
}
```

### Calling Functions

```c
int result = add(3, 5);
```

## Miscellaneous

### Comments

```c
// This is a single-line comment

/*
   This is a
   multi-line comment
*/
```

### Preprocessor Directives

```c
#include <stdio.h>   // Include standard input/output library
#define SIZE 10       // Define a macro constant
```

Remember to check the official C documentation for more details and advanced topics.
