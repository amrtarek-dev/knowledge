Some people though argue that `C++` is not a pure object-oriented Language. Reason being the use of `main()` function in `C++` that can exist without any Class. Since making a Class is not a primary requirement in `C++` hence it is considered a partial object-oriented language.

## Class
A class pulls together related data, and doing that makes the code easier to change and use.
- A customer's first name, last name, address, and phone number.

And it also holds class members (functions)
- get a customer's full name
- post a transaction to an account - including updating the balance.
- includes operator overloads (it just functions with wired names.) if those make sense.

### How to design a class
- generally, member variables are private. (encapsulation)
- functions you think of early are usually public.
- the helper functions are private.
- make one or more constructors to initialize the class, or initialize variables.

##  Encapsulation
it is not just to hide the data, it is to do not rely on data that can be changed later.
- by making the class logic private you are capsulate the logic to be hidden from the user and then you can change the logic as you want and the user will not be affected.

So to do so:
- Add as few public member functions as you can.
- Use private functions if you just want to keep from repeating code or give something a name (ex helper function)
- The more that is encapsulated, the better.
- changes in one part of the code don't affect other places.
- it is easier for the developer and less likely to cause bugs elsewhere.

## Inheritance (is-a) `:`

In C++ you can inherit a base class (parent) by using the `:` symbol, C++ supports multiple class inheritance.

``` cpp
// Base class  
class Vehicle {  
  public:  
    string brand = "Ford";  
    void honk() {  
      cout << "Tuut, tuut! \n" ;  
    }  
};  
  
// Derived class  
class Car: public Vehicle {  
  public:  
    string model = "Mustang";  
};  
  
int main() {  
  Car myCar;  
  myCar.honk();  
  cout << myCar.brand + " " + myCar.model;  
  return 0;  
}
```

### Type of Inheritance
Access specifiers are also to specify the type of inheritance:
- **Public Inheritance** (Recommended): public members of the base class become public member of the derived class and protected member of the base class become the protected members of the derived class, Private members are never accessible from the derived class.
- **Protected Inheritance**: Public and protected members of the base class become protected members of the derived class.
- **Private Inheritance** (Default): Public and protected members of the base class become private members of the derived class.

> Constructors and Destructors call orders for base and child class is:
> Constructor Base ->(Then)-> Constructor child, Destructor child ->  Destructor Base.


## Abstraction
It focuses on exposing only the essential features of an object or a class while hiding the irrelevant details by Focuses on "what" an object does. It simplifies the design by modeling real-world entities at a higher level.

### Abstract class (Interface)
> In C++ there is no concept called `interface`, interfaces were first introduced in Java to work around the lack of multiple inheritance.

You can achieve the Interface concept in CPP by making an abstract base class
> Abstract class in cpp is a class in which at least one member function is a `pure virtual function`

``` cpp
class IBase
{
	// pure virtual method
	virtual void Describe() = 0;

	// destructor, use it to call destructor of the inherit classes
	virtual ~IBase() {}; 
};
```
Abstract class can not be initiated (generate an object from it),
so it can not be used as a solid class, it has to be inherited and the child class has to implement the pure virtual function to be able to be initiated, or it will be an abstracted class too.

Abstract class must use a virtual destructor, and any child class has to implement the virtual function, or it will be an abstract class too, and you can not instantiate it (declare an object from it)

> If you do not add the virtual destructor in the interface, then the destructor of the inherited class is not called.


## Polymorphism

## Aggregation (has-a)
The whole-part relationship between two objects where one object (the whole) contains or references one or more instances of another object (the part).
And the lifetime of the part does not depend on the lifetime of the whole.

``` cpp
#include <vector>

class Book {
	// Engine properties and methods
};

class Library {
	// Aggregation: Library "has" books
	std::vector <Book*> books;
	public:
	void addBook(Book* book){
		books.push_back(book);
	}
};

int main(){
	Book book1;
	Book book2;

	Library lib;
	lib.addBook(book1);
	lib.addBook(book2);
	
	return 0;
}
```
## Composition (contains-a)
The life time of the part object is strictly tied to the whole's life-cycle.

``` cpp
#include <string>
#include <vector>

class Book {
	private:
	std::string title;
	public:
	Book(const std::string& bookTitle): title(bookTitle){}
	// Engine properties and methods
};

class Library {
	// Aggregation: Library "has" books
	std::vector <Book> books;
	public:
	void addBook(const std::string title){
		Book book(title);
		books.push_back(book);
	}
};

int main(){
	Library lib;
	lib.addBook("Book1");
	lib.addBook("Book2");
	
	return 0;
}
```