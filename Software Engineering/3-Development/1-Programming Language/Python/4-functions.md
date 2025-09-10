# Functions and Classes
Following Python Types and Flow Control, we may begin to learn more about Python scripts and creating functions and classes.

## Python Scripts

Python is a versatile and powerful programming language that allows you to write scripts to automate tasks, build applications, and solve complex problems. In this article, we will explore how to create functions and define classes in Python.

## Modularity

In all modern programming languages, it is common to have the ability to make different blocks of code which to reuse again in other places.

So Python is supporting three types of modularity: **functions**, **classes**, and **modules**.

### Functions

Functions in Python are blocks of reusable code that perform specific tasks. They help modularize your code and make it more organised and readable. Let's see an example of a function that calculates the factorial of a number:

```python
def factorial(n):
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result

# Type hints were added to the language through **PEP 484 – Type Hints (2015)**.
def factorial_with_type(n: int) -> int:
	result = 1
    for i in range(1, n + 1):
        result *= i
    return result
    
num = 5
fact = factorial(num)
print(f"The factorial of {num} is: {fact}")

fact = factorial_with_type(num)
print(f"The factorial of {num} is: {fact}")
```

In the above code, we define a function named **factorial** that takes a parameter **n**. 
It uses a **for** loop to calculate the factorial of **n** and returns the result. 
We then call the function with **num** set to 5 and print the output.

### Why are there types in Python code?

1. **Readability & Documentation**
``` python
def add(a: int, b: int) -> int:
	 return a + b
```
This makes it clear that `add` expects integers and returns an integer, even though Python doesn’t enforce it at runtime.

2. **Static Analysis / Linting**  
Tools like **mypy**, **Pyright**, or IDEs (VS Code, PyCharm) can check your code for type errors **before running** it.  
Example:  
``` python
def greet(name: str) -> str:
     return "Hello " + name  greet(123)  # IDE or mypy will flag this   
```
   
3. **Large Projects / Teamwork**  
 In big codebases, knowing variable types helps avoid mistakes and makes collaboration easier.

4. **Optional – Not Enforced**  
Types are only hints. At runtime Python still allows:
``` python
def add(a: int, b: int) -> int:
     return a + b  print(add("5", "6"))  # Works! (returns "56")
```
Python won’t stop it unless you use a type checker.


A **parameter** is an object that is included in a function definition for use in that function. When you define a function, you create variables in the function header. They can then be used in the body of the function.

n **argument** is the data brought into a function when it is called. When calling remaining_login_attempts in the following example, the integers 3 and 2 are considered arguments:
remaining_login_attempts(3, 2)

The return keyword is used to return information from a function.

A **global variable** is a variable that is available through the entire program. Global variables are assigned outside of a function definition.

A **local variable** is a variable assigned within a function. These variables cannot be called or accessed outside of the body of a function. Local variables include parameters as well as other variables assigned within a function definition.


## Built-in functions
Functions that exist within python and can be called directly.

- print()
- type()
- max(), min()
``` python
time_list = [12, 2, 32, 19, 57, 22, 14]
print(min(time_list))
print(max(time_list))
```
- sorted()
``` python
time_list = [12, 2, 32, 19, 57, 22, 14]
print(sorted(time_list))
print(time_list)

#[2, 12, 14, 19, 22, 32, 57]
#[12, 2, 32, 19, 57, 22, 14]
```


### String functions
**Bracket notation** refers to the indices placed in square brackets.
``` python
device_id = "h32rb17"
print("h32rb17"[0])
print(device_id[0])
```
- str() function converts its input object into a string.
- len() function, which returns the number of elements in an object
- .upper() method returns a copy of the string with all of its characters in uppercase.
- .lower() method returns a copy of the string in all lowercase characters
- .index() method finds the first occurrence of the input in a string and returns its location.

``` python
tshah_index = "tsnow, tshah, bmoreno - updated".index("tshah")
print(tshah_index)
# 7
```
- Concat 2 strings with + sign
``` python
print("Test"+"Me")

print("Security"[1:3])
// ec
```