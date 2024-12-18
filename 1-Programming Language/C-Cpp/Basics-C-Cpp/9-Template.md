# Template
is the way for generic programming.
it is a code that works independently of type.

- Template functions
- Template classes

it is where you find an angle bracket
```
template <typename Type> decleration
template <class Type> decleration
```

## Template function:
it looks like the normal function but preceded by **template** keyword and a set of type identifiers, which will be replaced during compilation with actual types.

``` cpp
template <typename T>
T maxof ( T a, T b) {
    return (a > b ? a : b);
}
```

## Template class
``` cpp
template <typename T>
class A {
    T a;
public:
    T getA() const { return a;}
    void setA(T x) { a = x;}
};
// OR

template <typename T>
class A {
    T a;
public:
    explicit A(int);
    T getA() const { return a;}
    void setA(T x) { a = x;}
};
// the definition
A<T>::A(int a = 10){}

// To use it you have to specify the template class type
A<int> obj(100);
// or 
A<int> obj = 100;
```
When a function or class is instantiated from a template the compiler generates specialisation from this function and the class specifically suited the type with instantiation. 

- Overuse of templates can lead to larger executables, longer build time.
- Because the compiler must generate specialisation for every call and instance of function and class.
- Confusing error messages

**Note** to guide the template type while instantiation.
```
string the_max = maxof<string> ("aaaa", "baaa");
```