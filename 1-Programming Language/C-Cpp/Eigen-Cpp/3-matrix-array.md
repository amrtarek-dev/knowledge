# Eigen Matrix and Arrays
The eigen library has made the matrix manipulation very easy and handy by providing multiple functions and operations to deal with matrix in c++.

## Types
Eigen providing two matrix types:
- Fixed size (Eigen::Matrix<n><datatype>)
- Dynamic size (Eigen::MatrixX<datatype>)

And every type supporting the numerical data type for C++
- Eigen::Matrix2d  is 2x2 matrix of type double
- Eigen::Matrix3d  is 3x3 matrix of type double
- Eigen::Matrix4d  is 4x4 matrix of type double
- Eigen::MatrixXd  is dynamic matrix of type double

And it  support the same functions for **float**, **complex float**, and **complex double**

- Eigen::Matrix2f  is 2x2 matrix of type float
- Eigen::Matrix2cf  is 2x2 matrix of type std::complex<float>

## Initialization
Eigen providing multiple option to initialize the matrix
### Zeros
To initialize a matrix to zeros
```cpp
Eigen::MatrixXd X = Eigen::MatrixXd::Zero(nrows, ncols);
// where nrows is the number of rows
// and ncols is the number of colums.

Eigen::MatrixXd X = Eigen::MatrixXd::Zero(3, 2);
Eigen::ArrayXXd a = Eigen::ArrayXXd::zero()
```
### Numbers
To initialize a matrix to specific values
```cpp
// Comma-initialization
Eigen::Matrix2d a;
  a << 1, 2,
       3, 4;
  Eigen::MatrixXd b(2,2);
  b << 2, 3,
       1, 4;
```

## Coefficient accessors
```cpp
#include <iostream>
#include <Eigen/Dense>
 
int main()
{
  Eigen::MatrixXd m(2,2);
  m(0,0) = 3;
  m(1,0) = 2.5;
  m(0,1) = -1;
  m(1,1) = m(1,0) + m(0,1);
  std::cout << "Here is the matrix m:\n" << m << std::endl;
  Eigen::VectorXd v(2);
  v(0) = 4;
  v(1) = v(0) - 1;
  std::cout << "Here is the vector v:\n" << v << std::endl;
}
```


## Convert from STL
To convert std::vector to Eigen::Vector

```cpp
int N = 100;
std::vector<float> v(N, 1.0f);
Eigen::VectorXf ev = Eigen::VectorXf::Map(&v[0], N);

// The generic formula
Eigen::VectorXf ev = Eigen::VectorXf::Map(&v[0], v.size());
```

## Convert to STL
To convert from Eigen::Vector to std::vector

```cpp
VectorXd firstEvector;
vector<double> vec2(firstEvector.data(), firstEvector.data() + firstEvector.size());

// Or 
vec.resize(firstEvector.size());
Map<VectorXd>(vec.data(), vec.size()) = firstEvector;
```


Or as a template function
```cpp
template<typename T>
std::vector<T> EigenRowMatrixToVecor(const Eigen::Matrix<T, Eigen::Dynamic, Eigen::Dynamic>& matrix)
{
if (matrix.cols() != 1)
    {
         throw "The matrix is not one row";
     }
     std::vector<std::complex<T>> eigenvalues;
     eigenvalues.resize(matrix.rows());
     for (auto value = 0; value < matrix.rows(); ++value)
     {
         eigenvalues[value] = matrix(value, 0);
      }
     return eigenvalues;      
}
```
