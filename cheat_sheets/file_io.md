# C File I/O Cheat Sheet

## File Handling Basics

### Opening a File

```c
#include <stdio.h>

FILE *filePointer;

// Open file for reading
filePointer = fopen("example.txt", "r");

// Open file for writing
filePointer = fopen("output.txt", "w");

// Open file for appending
filePointer = fopen("data.txt", "a");
```

### Closing a File

```c
fclose(filePointer);
```

## Reading from a File

### Reading Characters

```c
int ch = fgetc(filePointer);
while (ch != EOF) {
    // Process character
    ch = fgetc(filePointer);
}
```

### Reading Lines

```c
char buffer[100];
while (fgets(buffer, sizeof(buffer), filePointer) != NULL) {
    // Process line
}
```

## Writing to a File

### Writing Characters

```c
fputc('A', filePointer);
```

### Writing Strings

```c
fprintf(filePointer, "Hello, World!\n");
```

## Binary File I/O

### Reading Binary Data

```c
struct Record {
    int id;
    float value;
};

FILE *binaryFile = fopen("data.bin", "rb");
struct Record record;

fread(&record, sizeof(struct Record), 1, binaryFile);

fclose(binaryFile);
```

### Writing Binary Data

```c
struct Record {
    int id;
    float value;
};

FILE *binaryFile = fopen("data.bin", "wb");
struct Record record = {1, 3.14};

fwrite(&record, sizeof(struct Record), 1, binaryFile);

fclose(binaryFile);
```

## Error Handling

### Checking File Open Success

```c
filePointer = fopen("example.txt", "r");
if (filePointer == NULL) {
    perror("Error opening file");
    return 1;
}
```

### Checking File Close Success

```c
if (fclose(filePointer) != 0) {
    perror("Error closing file");
    return 1;
}
```

## Seeking in a File

### Setting File Position

```c
fseek(filePointer, 0, SEEK_SET);    // Set position to the beginning
fseek(filePointer, 10, SEEK_CUR);   // Move 10 positions forward
fseek(filePointer, -5, SEEK_END);   // Move 5 positions backward from the end
```

### Getting Current File Position

```c
long currentPosition = ftell(filePointer);
```

Remember to handle file I/O operations carefully, check for errors, and close files when done. Refer to the official C documentation for more in-depth information on file input and output.
```
