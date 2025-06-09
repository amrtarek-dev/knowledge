# Multible files and headers
we can make one single big file for the C++ project but if the project is big enough we need to split it into different files 
- to reduce the compilation time, just compile the file which has the edit.
- and to have coordinated the work of several developers on the same project.

## Build process
- Multiple files preprocessed.
- Multiple files compiled into object files,
- linker will link all object files with the libraries.
- then the executable will be produced.

## Header files
it is to collect the functions declaration.
- to make the project easy to maintain.
- to hide the more important code.

```
# sign is an instruction to the preprocessor - a step that runs before the compiler.
#include <>   // standard library or system library
#include ""   // this is a local library or header file.
#define
#ifdef
...
```
``

when you include a header file the entire file which you included is become pasted where the include statement written.

```
#pragma once
// this is the header file guard to do not include this header file more than one.
// it is not recommended in embedded development because it is not portable.
// use this instead.
#ifndef __FILE_NAME__
#define __FILE_NAME__
...
#endif
```

## Compiler Error
- You can forget to declare a function before you call it.
- forget to include the header
- Function is not declared in the header.

the compiler need only know that the function exists, it doesn't need to know about the body of the function or where it is.

## Linker Error
- When you forget to implement the function.
- So the code for that function is not in any of the Cpp files.
- Or you are not linking the .cpp file.