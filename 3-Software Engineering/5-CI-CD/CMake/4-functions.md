# CMake Functions
 Functions in CMake are reusable blocks of code that perform a specific task. They are defined using the **function** keyword followed by the function name and a list of arguments enclosed in parentheses. 
 
Functions in CMake are similar to functions in other programming languages, as they allow developers to encapsulate a piece of code and execute it multiple times.
There are two versions of funcions supported in CMake
 
- Built-in functions
- Custom Functions

## Built-in Functions
There are built-in functions that are pre-defined in the cmake script to help you build your build system easyer and faster.

### Variables functions

CMake also provides various functions and commands to manipulate variables. For example, the **get_variable()** command can be used to retrieve the value of a variable, while the **unset()** command can be used to remove a variable from the current scope. Additionally, CMake supports string manipulation functions, such as **string()** and **string(REGEX)**, which can be used to modify and extract information from variables that hold string values. Understanding these functions and commands is essential for effectively working with variables in CMake.

#### get_variable()
 You can use **get_variable()** function to retrieve the value of a variable in CMake as a new variable by get_variable(<the_original_variable> <value_as_a_new_variable>).

```cmake
set(myVariable "Hello, world!")
get_variable(myVariable TheValueVariable)
message("${TheValueVariable}") # Output: Hello, world!
```

 #### unset()
 You can use **unset()** function to remove a variable from the current scope in CMake.

```cmake
set(myVariable "Hello, world!")
unset(myVariable)
message("${myVariable}") # Output: (empty)
```

#### string()
You can use **string()** function to modify a string variable in CMake by string(REPLACE <old_word> <new_word> <ouput_variable> <targert_string>).

```cmake
set(myString "Hello, world!")
string(REPLACE "world" "CMake" myString ${myString})
message("${myString}") # Output: Hello, CMake!
```

#### string(REGEX)
You can use **string(REGEX)** function to extract information from a string variable by 
string(REGEX MATCH < word > <ouput_variable> <targert_string>).

```cmake
set(myString "Hello, CMake!")
string(REGEX MATCH "CMake" match ${myString})
message("${match}") # Output: CMake
```

### Build functions
The build functions are functions to automate the build process.
#### add_library
It is a CMake function to build a library
```cmake
add_library(libraryName
            [STATIC|SHARED|MODULE]
            [EXCLUDE_FROM_ALL]
            source1 source2 ......)
```
The first parameter to **add_library** is the name of the library **library name**, this can be any valid CMake name, and the **source1 source2** are the filenames for the compiled library and they have to be in your build directory, those are the mandatory parameters.

In addition, you may optionally add **STATIC**, **SHARED**, or **MODULES**, as a second parameter for the library type.

Following the type, you can also add **EXCLUDE_FROM_ALL** as another optional argument to avoid the library being built by default once you invoke **cmake --build**, However, this argument is ignored if the library is a dependancy for a target that is built by default.

### set_target_properties
This function will configure the build target to use custom options.
```cmake
set_target_properties(target1 target2 ...
                      PROPERTIES prop1 value1
                      prop2 value2 ...)
```
ex:
This will set the C++ standard to the library
```cmake
set_target_properties(${library_name} PROPERTIES
CXX_STANDARD 17
CXX_STANDARD_REQUIRED ON
)
```

#### target_include_directories
It is a CMake function to include the header files directories to a target
```cmake
target_include_directories(target_name {PUBLIC|PRIVATE|INTERFACE} directories)
```
#### target_link_libraries
It will tell the linker to link this library to this target.

#### find_package
It is used to search for cmake settings from external sourcess i.e outside of the project, if you want to link with a library without including the source of the library in a sub directory of the project. From a lower level point of view, **find_package(Foo)** looks for a cmake module **FinddFoo.cmake** and executes the module. The purpose of the module is to generate cmake variables or targets that can be used to include the corresponding dependency.
```cmake
find_package()
```
So it is searching for a library to build from its source code.

### Keys
The name of the function is descriptive of its functionality so you can sort it like:
- add_* : add target to the project
- target_* : add data to specific target
- *_include_*: for header files for the compiler
- *_link_*: for the linker
- *_directories: for directories

## Custom functions

To create the function you have to use the key word function to start the scope of the funcion and **endfunction()**
to close the scope of the function

```cmake
function(function_name INPUT argument1 argument2)
    ...
endfunction()
```

ex:
```cmake
function(add_numbers num1 num2)
    math(EXPR sum "${num1} + ${num2}")
    message("The sum of ${num1} and ${num2} is ${sum}")
endfunction()
```

To call the function with arguments
```cmake
add_numbers(5 7)
```

Output:
```cmake
The sum of 5 and 7 is 12
```

another ex:
```cmake
function(compare_numbers num1 num2)
    if(${num1} EQUAL ${num2})
        message("The numbers are equal")
        return 0
    else()
        message("The numbers are not equal")
        return 1
    endif()
endfunction()
```

Functions in CMake are a powerful tool for organizing and managing your build process. They allow you to encapsulate complex logic into reusable blocks, improving code readability and maintainability. 

By using functions, you can easily customize different parts of your build process based on specific requirements without duplicating code. Understanding how to define, call, and utilize functions in CMake is essential for effectively utilizing the capabilities of this build automation tool.