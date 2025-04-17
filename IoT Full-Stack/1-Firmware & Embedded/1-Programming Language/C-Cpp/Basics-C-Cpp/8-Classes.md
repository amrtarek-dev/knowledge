In C++, we have several different data types like `int`, `string`, `bool` etc. An object can be created out of any of those types. An _object_ is an instance of a class. Well, object-oriented programming wouldn’t make sense if we couldn’t make our own custom objects. This is where **classes** come into play.

Classes are used to create _user-defined data types._ We can use these basic data types to create our own class. The cool part is that our class can contain multiple variables, pointers, and functions which would be available to us whenever a class object is created.
## Class Declaration
A class in C++ is declared using the `class` keyword followed by the class name and a pair of curly braces that contain the members of the class.
``` cpp
class MyClass {
public:
    int myNumber;        // Public attribute
    void myFunction();   // Public method declaration
};
```

## Access Specifiers
- **public**: Members declared as `public` can be accessed from outside the class using `.` operator.
- **private**: Members declared as `private` can only be accessed from within the class itself (default access specifier).
- **protected**: Members declared as `protected` can be accessed within the class and by derived classes.

## Member Functions
Functions defined inside a class are called **member functions** or **methods**. They define the behavior of the objects.
``` cpp
class MyClass {
public:
    int myNumber;

    void myFunction() {
        cout << "Hello World!" << endl;
    }
};
```

## Use Class (Objects)
To use a class, you need to create objects (instances of the class).
``` cpp
MyClass myObj;
myObj.myNumber = 15;  // Accessing a public attribute
myObj.myFunction();   // Calling a public method
```

## Constructors
**Constructor**: A special member function that is called when an object is created. It is often used to initialise objects. The constructor has the **same name** as the class and **no return** type.
``` cpp
class MyClass {
public:
    int myNumber;

    // Constructor
    MyClass() {
        myNumber = 10;
    }
};
```

## Destructors
**Destructor**: A special member function that is called when an object is destroyed. It has the same name as the class preceded by a tilde `~` and no return type. It is used to free resources.
``` cpp
class MyClass {
public:
    // Destructor
    ~MyClass() {
        // Cleanup code
    }
};
```

## Member Initialisation List
Used to initialise class members directly before the constructor body executes.
``` cpp
class MyClass {
public:
    int myNumber;
    MyClass(int num) : myNumber(num) {}  // Constructor with initialization list
};
```


## Scope Resolution Operator `::`
The scope resolution operator (`::`) allows us to simply declare the member functions in the class and define them elsewhere in the code, using the following syntax:

``` cpp
class Rectangle {
  int length;
  int width;

  public:
  
  // We only write the declaration here
  void setLength(int l);
  int area();
};

// Somewhere else in the code
void Rectangle::setLength(int l){ // Using the scope resolution operator
  length = l;
}

int Rectangle::area(){
  return length * width; 
}
```

