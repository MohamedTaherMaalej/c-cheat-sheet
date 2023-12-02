# C Standard Library (stdlib.h) Cheat Sheet

## General Utilities

### `exit` - Exit Program

```c
#include <stdlib.h>

exit(EXIT_SUCCESS);   // Exit program successfully
exit(EXIT_FAILURE);   // Exit program with failure
```

### `abort` - Abnormal Program Termination

```c
#include <stdlib.h>

abort();   // Abnormally terminate the program
```

### `atexit` - Register Function to be Called at Exit

```c
#include <stdlib.h>

void cleanupFunction() {
    // Code to be executed at program exit
}

int main() {
    atexit(cleanupFunction);
    return 0;
}
```

## Dynamic Memory Management

### `malloc` - Allocate Memory

```c
#include <stdlib.h>

int* ptr = (int*)malloc(sizeof(int));  // Allocate memory for an integer
```

### `calloc` - Allocate Contiguous Memory

```c
#include <stdlib.h>

int* arr = (int*)calloc(5, sizeof(int));  // Allocate memory for an array of 5 integers
```

### `realloc` - Reallocate Memory

```c
#include <stdlib.h>

int* resizedArr = (int*)realloc(arr, 10 * sizeof(int));  // Resize the array to accommodate 10 integers
```

### `free` - Free Allocated Memory

```c
#include <stdlib.h>

free(ptr);  // Free the memory allocated for a single integer
free(arr);  // Free the memory allocated for an array
```

## Sorting and Searching

### `qsort` - Quick Sort

```c
#include <stdlib.h>

int compareFunction(const void* a, const void* b) {
    return (*(int*)a - *(int*)b);
}

int array[] = {4, 2, 8, 5, 1, 7};
int n = sizeof(array) / sizeof(array[0]);

qsort(array, n, sizeof(int), compareFunction);
```

### `bsearch` - Binary Search

```c
#include <stdlib.h>

int values[] = {1, 2, 3, 4, 5};
int key = 3;

int* result = (int*)bsearch(&key, values, 5, sizeof(int), compareFunction);
```

## Pseudo-Random Number Generation

### `rand` - Generate Random Number

```c
#include <stdlib.h>

int randomNumber = rand();   // Generate a pseudo-random integer
```

### `srand` - Seed Random Number Generator

```c
#include <stdlib.h>
#include <time.h>

srand(time(NULL));   // Seed the random number generator with the current time
```

This cheat sheet provides a quick reference for commonly used functions from the C Standard Library (stdlib.h). Customize it based on your preferences and specific needs. Refer to the official C documentation for more in-depth information on each function.
