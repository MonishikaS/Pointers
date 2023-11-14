The malloc function in C is used for dynamic memory allocation. It stands for "memory allocation" and is part of the standard C
library (stdlib.h). The primary purpose of malloc is to allocate a block of memory of a specified size during the program's 
execution. 
```c
#include <stdlib.h>

void* malloc(size_t size);
```
The malloc function takes one argument: size, which specifies the number of bytes to allocate.

It returns a pointer to the beginning of the allocated memory block. The return type is void*, which means that it can be 
implicitly cast to a pointer of any data type.
