# CMake Variables

Variables in CMake play a crucial role in defining and manipulating data that is used throughout the build process. They are used to store values that can be accessed and modified as needed. 
## Variables types

There are two types of the variables in CMake:
- Built-in variables
- Custome variables (User defined variables)

### Built-in variables
[Useful variables](https://gitlab.kitware.com/cmake/community/-/wikis/doc/cmake/Useful-Variables)

### User defined
CMake variables are case-sensitive and are defined using the **set()** command. Variables in CMake can hold various types of data, such as **strings**, **numbers**, **lists**, and even other variables. 

There are 3 ways to make a variable in CMake
- set()
- string()
- list()

#### set()
You can make a string variable by using set()
```cmake
set(MyString "Some Text")
message("${MyString}") # Output: Some Text

# With variable
set(MyStringWithVar "Some other Text ${MyString}")
message("${MyStringWithVar}") # Output: Some other Text Some Text

# To have the Quotes in the string
set(MyStringWithQuot "Some qoute \"${MyStringWithVar}\"")
message("${MyStringWithVar}") # Output: Some other Text Some Text
```

[Continue this] (https://stackoverflow.com/questions/31037882/whats-the-cmake-syntax-to-set-and-use-variables)


## Variables scope
Variables can have different scopes, such as global scope or local scope. Global scope variables are accessible throughout the entire CMake project, while local scope variables are only accessible within a specific scope, such as a function or a block of code. It is important to understand the scope of variables to ensure that they are used correctly and avoid any unintended side effects or conflicts with other variables.

#### Global variables


#### Env
To get variable from the environment variables
```cmake
$ENV{EnvironmentVarirableName}
```

Overall, variables in CMake are a fundamental concept that allows for flexible and dynamic configuration of build processes.
They provide a way to store and manipulate data that is used throughout the project. 
Understanding the syntax and usage of variables in CMake is crucial for effectively configuring and building projects using CMake.