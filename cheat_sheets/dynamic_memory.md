# C Dynamic Memory Allocation Cheat Sheet

## Allocating Memory

### `malloc` - Memory Allocation

```c
#include <stdlib.h>

int* ptr = (int*)malloc(sizeof(int));  // Allocate memory for an integer
```

### `calloc` - Contiguous Allocation

```c
int* arr = (int*)calloc(5, sizeof(int));  // Allocate memory for an array of 5 integers
```

## Reallocating Memory

### `realloc` - Reallocate Memory

```c
int* resizedArr = (int*)realloc(arr, 10 * sizeof(int));  // Resize the array to accommodate 10 integers
```

## Freeing Allocated Memory

### `free` - Free Allocated Memory

```c
free(ptr);  // Free the memory allocated for a single integer
free(arr);  // Free the memory allocated for an array
```

## Memory Initialization

### Initializing Allocated Memory

```c
int* initializedArr = (int*)calloc(5, sizeof(int));  // Allocating and initializing an array

for (int i = 0; i < 5; i++) {
    initializedArr[i] = i + 1;  // Initializing each element
}
```

## Memory Deallocation Practices

### Check for Allocation Success

```c
int* ptr = (int*)malloc(sizeof(int));
if (ptr == NULL) {
    // Allocation failed
    perror("Memory allocation failed");
    exit(EXIT_FAILURE);
}
```

### Free Memory When Done

```c
free(ptr);  // Free the allocated memory when it is no longer needed
```

### Avoid Memory Leaks

Always free dynamically allocated memory to prevent memory leaks. Leaked memory can lead to performance issues and program instability.

## Memory and Strings

### `strcpy` - Copy Strings

```c
#include <string.h>

char source[] = "Hello, World!";
char* destination = (char*)malloc(strlen(source) + 1);  // Allocate memory for the destination string

strcpy(destination, source);  // Copy the source string to the destination
```

### `strcat` - Concatenate Strings

```c
char str1[20] = "Hello, ";
char str2[] = "World!";
char* result = (char*)malloc(strlen(str1) + strlen(str2) + 1);  // Allocate memory for the result string

strcpy(result, str1);  // Copy the first string
strcat(result, str2);  // Concatenate the second string
```

Remember to free dynamically allocated memory to prevent memory leaks. Use these practices judiciously and refer to the official C documentation for more in-depth information on dynamic memory allocation.
