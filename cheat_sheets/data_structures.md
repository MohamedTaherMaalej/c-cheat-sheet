# C Data Structures Cheat Sheet

## Arrays

### Declaration and Initialization

```c
int numbers[5];             // Declaration of an integer array
int values[] = {1, 2, 3};    // Declaration and initialization
```

### Accessing Elements

```c
int x = numbers[2];         // Accessing the third element
```

### Multi-dimensional Arrays

```c
int matrix[3][3];           // Declaration of a 3x3 matrix
matrix[0][0] = 1;            // Accessing and modifying elements
```

## Structures

### Declaration and Initialization

```c
struct Point {
    int x;
    int y;
};

struct Point p1 = {3, 4};    // Initialization of a structure variable
```

### Accessing Members

```c
int xCoord = p1.x;           // Accessing structure members
```

### Nested Structures

```c
struct Rectangle {
    struct Point topLeft;
    struct Point bottomRight;
};
```

## Linked Lists

### Node Structure

```c
struct Node {
    int data;
    struct Node* next;
};
```

### Creating a Linked List

```c
struct Node* head = NULL;    // Initializing an empty linked list
```

### Inserting a Node

```c
struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
newNode->data = 42;
newNode->next = NULL;

// Insert at the beginning
newNode->next = head;
head = newNode;
```

### Traversing a Linked List

```c
struct Node* current = head;
while (current != NULL) {
    // Process current node
    current = current->next;
}
```

## Stacks

### Stack Implementation using Arrays

```c
#define MAX_SIZE 100

struct Stack {
    int array[MAX_SIZE];
    int top;
};

void push(struct Stack* stack, int value) {
    if (stack->top < MAX_SIZE - 1) {
        stack->top++;
        stack->array[stack->top] = value;
    }
}

int pop(struct Stack* stack) {
    int value = -1; // Default value for an empty stack
    if (stack->top >= 0) {
        value = stack->array[stack->top];
        stack->top--;
    }
    return value;
}
```

## Queues

### Queue Implementation using Arrays

```c
#define MAX_SIZE 100

struct Queue {
    int array[MAX_SIZE];
    int front, rear;
};

void enqueue(struct Queue* queue, int value) {
    if (queue->rear < MAX_SIZE - 1) {
        queue->rear++;
        queue->array[queue->rear] = value;
    }
}

int dequeue(struct Queue* queue) {
    int value = -1; // Default value for an empty queue
    if (queue->front <= queue->rear) {
        value = queue->array[queue->front];
        queue->front++;
    }
    return value;
}
```

Remember to handle dynamic memory allocation carefully (freeing memory) and consider error handling in real-world scenarios. Refer to the official C documentation for more in-depth information on data structures in C.
