# Eigen Vector
The eigen library has made the Vector manipulation very easy and handy by providing multiple functions and operations to deal with Eigen vectors in c++.

## Types
Eigen providing two vector types:
- Fixed size (Eigen::Vector<n><datatype>)
- Dynamic size (Eigen::VectorX<datatype>)

And every type supporting the numerical data type for C++
- Eigen::Vector2d  is 2x0 Vector of type double
- Eigen::Vector3d  is 3x0 Vector of type double
- Eigen::Vector4d  is 4x0 Vector of type double
- Eigen::VectorXd  is dynamic Vector of type double

And it  support the same functions for **float**, **complex float**, and **complex double**

- Eigen::Vector2f  is 2x2 vector of type float
- Eigen::Vector2cf  is 2x2 vector of type std::complex<float>

## Initialization
Eigen providing multiple option to initialize the vector
### Zeros
To initialize a vector to zeros
```cpp
Eigen::VectorXd X = Eigen::VectorXd::Zero(nrows);
// where nrows is the number of rows
```
### Numbers
To initialize a vector to specific values
```cpp
Eigen::Vector2d a;
  a << 1, 2;
  Eigen::VectorXd b(2);
  b << 2, 3;

Vector2d a(5.0, 6.0);
Vector3d b(5.0, 6.0, 7.0);
Vector4d c(5.0, 6.0, 7.0, 8.0);
```

## Merge Vectors
```cpp
VectorXd vec_joined(vec1.size() + vec2.size());
vec_joined << vec1, vec2;
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
