# C Pointers Cheat Sheet

## Pointers Basics

### Declaration and Initialization

```c
int *ptr;       // Declaration of an integer pointer
int x = 5;
ptr = &x;       // Initialization with the address of x
```

Shortcut for declaration and initialization:

```c
int *ptr = &x;  // Declaration and initialization in one line
```

### Accessing Value and Address

```c
int value = *ptr;  // Dereferencing pointer to get the value
printf("Value: %d\n", value);

printf("Address: %p\n", (void *)ptr);  // Printing address
```

## Pointer Arithmetic

### Increment and Decrement

```c
int arr[5] = {1, 2, 3, 4, 5};
int *p = arr;

p++;   // Moves to the next element in the array
p--;   // Moves to the previous element in the array
```

### Array Access via Pointers

```c
int arr[3] = {10, 20, 30};
int *p = arr;

printf("%d\n", *p);   // Prints 10 (value at arr[0])
p++;                   // Moves to the next element
printf("%d\n", *p);   // Prints 20 (value at arr[1])
```

## Pointers and Functions

### Passing Pointers to Functions

```c
void modifyValue(int *ptr) {
    *ptr = 42;
}

int main() {
    int x = 10;
    modifyValue(&x);
    printf("Modified value: %d\n", x);
    return 0;
}
```

### Returning Pointers from Functions

```c
int* createArray(int size) {
    int *arr = (int*)malloc(size * sizeof(int));
    // Populate the array or perform other operations
    return arr;
}

// Don't forget to free the allocated memory when done.
```

## Dynamic Memory Allocation

### Allocating Memory

```c
int *ptr = (int*)malloc(sizeof(int));
```

### Freeing Allocated Memory

```c
free(ptr);
```

## Pointer to Functions

### Declaration and Usage

```c
int add(int a, int b) {
    return a + b;
}

int (*ptr)(int, int);   // Pointer to a function taking two ints and returning an int
ptr = &add;             // Assigning the address of the function
int result = ptr(3, 5);  // Calling the function via the pointer
```

Remember to handle pointers carefully to avoid memory leaks and undefined behavior. Refer to the official C documentation for more in-depth information on pointers and memory management.

