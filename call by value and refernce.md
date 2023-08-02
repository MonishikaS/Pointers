### CALL BY VALUE

In C programming, "call by value" refers to the way function arguments are passed to functions. When you pass arguments to a function by value, 
a copy of the argument's value is made and provided to the function. This means that changes made to the parameter inside the function do not affect the original value 
of the argument outside the function. 

Here's an example to illustrate call by value:

```c
#include <stdio.h>

void modifyValue(int x) {
    x = x * 2;
    printf("Inside function: x = %d\n", x);
}

int main() {
    int num = 5;
    printf("Before function call: num = %d\n", num);
    
    modifyValue(num);
    
    printf("After function call: num = %d\n", num);
    
    return 0;
}
```

In this example, the `modifyValue` function takes an argument `x` by value. When the `num` variable is passed to this function, a copy of the value `5` 
is made and stored in `x`. Any changes made to `x` inside the function do not affect the original `num` variable outside the function. As a result, the output will be:

```c
Before function call: num = 5

Inside function: x = 10
After function call: num = 5
```

As you can see, the value of `num` remains unchanged even though `x` was modified within the function.

To summarize, in call by value, a copy of the argument's value is passed to the function, and modifications to the parameter within the function do not affect the 
original argument outside the function.

### CALL BY REFERNCE
In C, there is no direct support for "call by reference" like some other programming languages (e.g., C++ or Python). However, you can simulate call by reference behavior using pointers. By passing a pointer to a variable as an argument to a function, you can modify the value of the variable directly within the function, thus achieving a similar effect to call by reference.

Here's an example to illustrate how to achieve call by reference using pointers:

```c
#include <stdio.h>

void modifyValueByReference(int *x) {
    *x = *x * 2;
    printf("Inside function: *x = %d\n", *x);
}

int main() {
    int num = 5;
    printf("Before function call: num = %d\n", num);
    
    modifyValueByReference(&num);
    
    printf("After function call: num = %d\n", num);
    
    return 0;
}
```

In this example, the `modifyValueByReference` function takes a pointer to an integer (`int *x`) as its parameter. 
This pointer refers to the memory location of the `num` variable in the `main` function. By dereferencing the pointer with `*x`, you can access and modify 
the actual value of `num` directly in memory. The `&num` passed to the function in the `main` function is the address of the `num` variable.

The output will be:

```
Before function call: num = 5
Inside function: *x = 10
After function call: num = 10
```

As you can see, the value of `num` is modified directly within the function using the pointer, achieving a behavior similar to call by reference.

Remember that while this approach simulates call by reference behavior, it's important to handle pointers carefully to avoid unintended memory-related issues 
like segmentation faults or undefined behavior.
