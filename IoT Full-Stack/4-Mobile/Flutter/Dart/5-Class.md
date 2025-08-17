The class is a blue print from an object
- A class defines properties and behaviors
- An object is a specific instance of a class.

Class defining:
- Properties (Attributes)
- Methods
- Object access (Public, private)

```dart
class Person {
	// Properties (Attributes)
	// Public
	String name;
	int age;
	// private
	int _number;

	//methods
	void showOutPut() {
		print(name);
		print(age);
	}
}

class MyPerson {
	String name;
	int age;

	// Default Constructor
	MyPerson(String name, [int age = 18]) {
		this.name = name;
		this.age = age;
	}
	// Or 
	// MyPerson(this.name, [this.age = 10]);

	//methods
	void showOutPut() {
		print(name);
		print(age);
	}
}

void main() {
	Person person1 = Person();
	person1.name = 'Amr';
	person1.age = 35;
	person1.showOutPut(); // Amr    35

	var person2 = MyPerson("Amr");
	person2.showOutPut();  // Amr   18
}
```


### Getters and Setters
- Getters perform calculations or formating
- Setters validate input or trigger actions

``` dart
class Rectangle {
	double _height;
	double _width;

	void set height(doubble value){
		if(value > 0){
			_height = value;
		}
	}
	void set width(doubble value){
		if(value > 0){
			_width = value;
		}
	}
	
	double get area => _height * width;
}

void main() {
	Rectangle r = Rectangle();
	r.width = 5;
	r.height = 5;
	print(r.area); // 25
}
```

### Static 
A call without creating an instance of the class.
- Do not belong to object instances
- Are used for utility functions
- Do not require object access

Example:
- Utility conversions
- Mathematical calculations

``` dart
class Math {
	static double pi = 3.14;
	static int square(int x){
		return x * x;
	}
}

void main() {
	print(Math.pi); // Output: 3.14
	print(Math.square(4)); // 16
}
```

## Encapsulation
using set and get to access the attributes

## Inheritance
Class inherits from the parent class
- Helps organize complex code
- Establishes relationships between parent and child classes
``` dart
class Animal {
	void eat() {
		print('Animal is eating');
	}
}

class Dog extends Animal {
	void bark() {
		print('Dog is barking');
	}
}
```