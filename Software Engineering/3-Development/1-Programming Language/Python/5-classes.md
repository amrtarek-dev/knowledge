
Classes in Python provide a way to define objects with their properties (attributes) and behaviors (methods). They are essential for object-oriented programming. Let's create a class to represent a car:

```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year
        self.speed = 0
    
    def accelerate(self, increment):
        self.speed += increment
    
    def brake(self, decrement):
        self.speed -= decrement
    
    def get_speed(self):
        return self.speed

# Creating an instance of the Car class
my_car = Car("Ford", "Mustang", 2022)

# Accessing attributes and calling methods
print(f"Make: {my_car.make}")
print(f"Model: {my_car.model}")
print(f"Year: {my_car.year}")

my_car.accelerate(20)
print(f"Current speed: {my_car.get_speed()} mph")

my_car.brake(10)
print(f"Current speed: {my_car.get_speed()} mph")
```

In the above code, we define a class named **Car** with attributes such as **make**, **model**, **year**, and **speed**. The **_ _ init _ _** method is a special method called the constructor, which initializes the object with the provided values. The class also has methods like **accelerate**, **brake**, and **get_speed** to manipulate and retrieve the car's speed.

We then create an instance of the **Car** class with the **my_car** object, passing the make, model, and year as arguments. We can access the attributes using dot notation and call the methods on the object.

### Python scripts (Modules)

A module is a file containing Python code that defines functions, classes, and variables. Modules provide a way to organize related code into separate files, making it easier to manage and reuse code across different projects. By importing a module, you can access its contents and utilize its functionality within your program.

Python modules can be created by simply creating a new **.py** file and defining the desired code within it. For example, you can create a module named **my_module.py** that contains various functions and classes. Then, in another Python script, you can import and use the functions and classes defined in **my_module.py**.

Here's an example of a module named **my_module.py**:

```python
def greet(name):
    print(f"Hello, {name}!")

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduce(self):
        print(f"My name is {self.name} and I am {self.age} years old.")
```

And here's an example of how to import and use the module in another Python script:

```python
import my_module

my_module.greet("Alice")

alice = my_module.Person("Alice", 25)
alice.introduce()
```

In the above code, we import the **my_module** module using the **import** statement. Then, we can access the functions and classes defined in the module using the module name as a prefix. We call the **greet** function and create an instance of the **Person** class, and utilize their respective functionalities.

When you create a Python script (module) there are some default objects that will be default in the script, even if you didn't write them down. they called the **built-in objects**.

it always starts with the double underscore then the object name then another double underscore, They called **Dunder methods**

#### Dunder methods
Dunder (Double Underscore) methods are special methods that are surrounded by double underscores (e.g., `__name__`,`__main__`,`__init__`, `__str__`, `__add__`). These methods have predefined names and are used to provide specific functionality to classes.

For example, the **`__init__`** method is a dunder method that is called when an object is created from a class. It initializes the object's attributes and sets their initial values. The **`__str__`** method is another dunder method that returns a string representation of the object when the str() function is called on it. the **`__name__`** method represents the name of the block, for example, if it is in a function it will return the function name, if it is in a script it will return the script name.

Dunder methods allow classes to define their behavior for built-in Python operations. For instance, the **`__add__`** method defines the behavior of the + operator for instances of a class, enabling custom addition logic.

By implementing dunder methods in your classes, you can customize how instances of those classes behave and interact with built-in Python operations, such as printing objects, performing mathematical operations, iterating over objects, and more.

Overall, modules provide a way to organize and reuse code, while dunder methods allow you to define special behaviors and operations for your classes.
By leveraging functions and classes, you can build complex programs and applications in Python that are easier to understand, maintain, and extend.