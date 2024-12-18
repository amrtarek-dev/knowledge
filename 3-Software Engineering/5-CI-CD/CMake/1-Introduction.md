# CMake introduction

CMake stands for **Cross-platform make** which is an open-source, cross-platform tool that is used for building, testing, and packaging software. 

It was first developed in **2000** by **Andy Cedilnik at Kitware**. 

CMake is a build automation tool that works by generating native build files such as Makefiles, Visual Studio solution files, and Xcode project files based on a simple configuration file called CMakeLists.txt. 

CMake is designed to be platform-independent, meaning it can generate build files for various build systems, such as Makefile for Unix-like systems and Visual Studio solution files for Windows.

## How to use it
To use CMake, developers need to create a **CMakeLists.txt** file that describes the project and its dependencies. The file typically includes information such as the **project name**, **the version number**, **the source files**, and **any external libraries** that are required. 
Once the **CMakeLists.txt** file is created, developers can run the **cmake** command to generate the build files for their platform and compiler. 
They can then use the generated files to build and test their software.

## CMake scripts
CMake scripts are written in the **CMake language**, which is designed to be **simple** and **easy** to understand. The syntax is based on a **series of commands** and **variables** that are used to define the build process. 

These commands and variables are used to specify the **source files**, **set compiler options**, **define dependencies**, and **generate** the build files for the target platform.


## CMakeLists.txt
```cmake
# The minimum cmake version required to run this cmake file.
cmake_minimum_required(VERSION 3.12)

# The project name, version, and the used programming language.
project(My_project VERSION 1.0 LANGUAGES CXX)

# Make (Generate) a library from this source files.
add_library(my_lib STATIC my_lib_source.cpp)

# Ask cmake to use this directory to get the header files for the library.
target_include_directories(my_lib PUBLIC directory_has_headers)

# Make (Generate) an Executable from this source files.
add_executable(my_program main.cpp)

# Ask cmake to use these directories to get the header files for the executable.
target_include_directories(my_program PRIVATE
    first_dir/
    second_dir/)

# Ask cmake to link this external libraries.
target_link_libraries(my_program PRIVATE my_lib)
```
