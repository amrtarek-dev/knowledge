
### Class
The class is a blue print from an object
```dart
class Person {
	String name;
	int age;

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


