# Cmake flow control
 Flow control in CMake is used to make decisions and execute specific commands or set variables based on conditions.

Cmake supports multiple technique to control the flow of the CMake script
- if conditions
- foreach
- while
- Generator Expression

## If conditions
if the condition is evaluated the condition and depend on the result it will decide to continue or make something else.
```cmake
if (WIN32)
    # Do something related to Windows build
elseif(UNIX)
    # Do something related to Linux build
endif()
```
### Logic operations
CMake supports **AND** and **OR** operations
```cmake
if(WIN32 OR UNIX)
    # Do something when building Windows or Linux-based machines.
endif() 
```
### Comparisons:

``` CMake
if(${Var} EQUAL value)
```
True if the given string or variable's value is a valid number and equal to that on the right.

``` CMake
if(${Var} STREQUAL "stringValue")
```
True if the given string or variable's value is lexicographically equal to the string or variable on the right.

``` CMake
if(${Var} LESS_EQUAL value)
```
New in version 3.7: True if the given string or variable's value is a valid number and less than or equal to that on the right.

``` CMake
if(${Var} GREATER_EQUAL value)
```
New in version 3.7: True if the given string or variable's value is a valid number and greater than or equal to that on the right.

``` CMake
if(${Var} GREATER value)
```
True if the given string or variable's value is a valid number and greater than that on the right.

``` CMake
if(${Var} LESS value)
```
True if the given string or variable's value is a valid number and less than that on the right.

## Generator Expression
> Generator expressions can not be printed by **message()** because it is evaluated during generating the build system, not during processing the **CMakeLists.txt**


There are two forms of generator expression are supported
- $<condition:true_string>
- $<IF:condition, true_string, false_string>

so the basic concept for both is the same, but one for only the true condition, and the other for the true, false condition, let's see example:

```cmake
# To check if the build type is debug or release
$<$<CONFIG:Debug>:DEBUG_MODE>
# This will return DEBUG_MODE only when the build type is debugging and an empty string if not.
```
> WARNING: Generator Expression is using specific expressions to make the comparison, so it is not supporting the custom variable names. the full list of supported expressions is [HERE](https://cmake.org/cmake/help/latest/manual/cmake-generator-expressions.7.html#id20)

 