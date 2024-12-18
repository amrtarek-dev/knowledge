Functions in C and C++ are essential building blocks of programs, enabling code modularity, reuse, and clarity. It is better to use it to don't repeat yourself, by avoiding duplication of the code.
While the fundamental concepts are similar in both languages, there are some differences due to C++ being an object-oriented language. Let's explore functions in both languages.
## Basics
A function is a block of code that performs a specific task.

> return_type function_name(parameters) {
    // code
    return value;  // if return_type is not void
    }

``` cpp
int add(int a, int b) {
    return a + b;
}
```
To use a function you need to call it, but the compiler needs to know it before you use it, that names **Declare** it, and somewhere in your program you have to implement it, so this is called **define** it.
### Function Declaration (Prototype)
Declares the function before its use in the code
> return_type function_name(parameters);

``` cpp
int add(int, int);
```

### Function Definition
This is where the actual code of the function is written
``` cpp
int add(int a, int b) {
    return a + b;
}
```

### Function Call
Functions are called by their name followed by parentheses enclosing arguments (if any).
``` cpp
int sum = add(5, 3);
```

### Parameter Passing
- **Pass by Value**: The function gets a copy of the arguments (default in both C and C++).
- **Pass by Reference** (C++ only): The function gets a reference to the actual argument.
``` c
void modifyValue(int a) {
    a = 10;  // This won't change the actual variable.
}
```
Example in C++ (Pass by Reference)
``` cpp
void modifyValue(int &a) {
    a = 10;  // This will change the actual variable.
}
```

### Default Arguments (C++ Only)
C++ allows functions to have default arguments
``` cpp
int add(int a, int b = 10) {
    return a + b;
}

int c = add(1); // c = 11
int d = add(1, 20); // d = 21
```
