# Eigen Library
It is very power full C++ library for reliable and fast linear algebra calculations and vectors and matrices manipulation.

## Start 
To start using eigen library you can download the source code from [Eigen download] (https://eigen.tuxfamily.org/) , you do not need to compile the library, just put the library path to your project and you are ready to go.
```bash
g++ -std=c++11 -I <path to eigen lib> executable_name filename.cpp
# For Example
g++ -std=c++11 -I lib/eigen-3.4.0/eigen-3.4.0/ eigen_test.cpp -o eigen
```

## Modules
Eigen library is divided in a core modules and several additional modules, each module has a corresponding header file which has to be included in order to use the module, there are two main header file which provide multiple modules which are:
- Dense: includes Core, Geometry, LU, Cholesky, SVD, QR and Eigenvalues header files
- Eigen: includes Dense and Sparse header files ( the whole Eigen library)


## Matrix
Eigen provide two version of matrix, **dynamic matrix** (Eigen::MatrixXd) and the **static matrix** (Eigen::Matrix2d, Matrix3d, Matrix4d), let us see an example to manipulate a matrix by the eigen library

```cpp
#include <Eigen/Dense>
#include <iostream>

int main(int argc, char** argv) {
    // initializing a dynamic matric
    Eigen::MatrixXd m1(2,3);
    m1 << 1,2,3,
          4,5,6;
    std::cout << "m1  = " << m1 << std::endl;
    std::cout << "m1 rows : " << m1.rows() << std::endl;
    std::cout << "m1 cols : " << m1.cols() << std::endl;
    return 0;  
}
```
So this will make a dynamic matric called **m1** and initialize it and then printing it.

```bash
m1  = 
1 2 3
4 5 6
m1 rows : 2
m1 cols : 3
```

## Vectors
Let us see another example to manipulate a vector by the eigen library.

```cpp
#include <Eigen/Dense>

int main(int argc, char** argv) {
    // initializing a dynamic vector
    Eigen::VectorXd v1(3);
    v1 << 2,1,2;
    std::cout << ""v1  = " << v1 << std::endl:
    std::cout << "v1 rows : " << v1.rows() << std::endl;
    std::cout << "v1 cols : " << v1.cols() << std::endl;
    return 0;  
}
```
So this will make a dynamic vector called **V1** and initialize it and then print it.

```bash
v1  = 
2
1
2
m1 rows : 3
m1 cols : 1
```

## Arrays
It is a general purpose arrays, that you can use to make both Vector and Matrix, but **Array** class provide an easy way to perform coefficient-wise operation, like adding a constant to every coefficient in the array,

```cpp
#include <Eigen/Dense>

int main(int argc, char** argv) {
    // initializing a dynamic array
    Eigen::ArrayXd a1(3);
    a1 << 2,1,2;
    std::cout << ""a1  = " << a1 << std::endl:
    std::cout << "a1 rows : " << a1.rows() << std::endl;
    std::cout << "a1 cols : " << a1.cols() << std::endl;

    Eigen::ArrayXXd b1(2,3);
     b1 << 1,2,3,
          4,5,6;
    std::cout << "b1  = " << b1 << std::endl:
    std::cout << "b1 rows : " << b1.rows() << std::endl;
    std::cout << "b1 cols : " << b1.cols() << std::endl;
    return 0;  
}
```
This will print
```bash
a1  = 
2
1
2
a1 rows : 3
a1 cols : 1
b1  = 
1 2 3
4 5 6
b1 rows : 2
b1 cols : 3
```

## Matrix multiplication
To multiply matrix you can treat it as a normal variable so you can do this as a continue of the above code.
```cpp
Eigen::MatrixXd p1 = m1 * v1:
std::cout << ""p1  = " << p1 << std::endl:
std::cout << "p1 rows : " <<p1.rows() << std::endl;
std::cout << "p1 cols : " << p1.cols() << std::endl;
```
So the star operator is overloaded so it will make matrix vector multiplication.

```bash
p1 =
10
25
p1 rows : 2
p1 cols : 1
```
