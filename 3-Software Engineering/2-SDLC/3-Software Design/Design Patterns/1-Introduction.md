# Start with Design Pattern

Design patterns are reusable solutions to common problems that software developers encounter during the design and implementation of software systems. 

They are tried-and-tested solutions that provide a template for solving specific issues in a structured and efficient way. These patterns help in creating maintainable, scalable, and flexible software architectures.

## Why design patterns 

Design patterns serve several purposes:

### Standardisation:
They offer standardised solutions to recurring design problems, making it easier for developers to communicate and understand each other's code.

### Code Reusability: 
Design patterns promote code reuse, reducing redundancy and promoting efficient development by leveraging established solutions rather than reinventing the wheel.

### Scalability and Maintainability: 
By following established patterns, software architectures become more scalable and maintainable, easing future modifications or enhancements.

### Best Practices: 
They encapsulate best practices and proven techniques that have evolved over time through experience, enhancing the quality of software development.

## When we can use design patterns 

Design patterns are applied across various stages of software development, including:

**Creation Patterns**: These patterns focus on object creation mechanisms, such as Singleton, Factory, Builder, etc., ensuring flexible and efficient object creation.

**Structural Patterns**: They deal with class and object composition to form larger structures, like Adapter, Decorator, Facade, etc., enhancing flexibility and efficiency in designing software architectures.

**Behavioral Patterns**: These patterns are concerned with algorithms and communication between objects, such as Observer, Strategy, Command, etc., facilitating the interaction and responsibilities of objects.

Developers use design patterns when faced with recurring problems in software development. They help in organizing code, reducing errors, and improving overall software quality. 

However, it's essential to use design patterns judiciously, as their overuse can lead to overly complex or convoluted code. Understanding the problem context and selecting the appropriate pattern is crucial for successful implementation.

## Basic UML ASCII Art
We will use a simple class diagram using ASCII art to show the diagram of the patterns, but we will mention the diagram components meaning below.

### Class Diagram
```md
+-------------------+
|  ClassName        |
+-------------------+
| - private_member  |
+-------------------+
| + public_method() |
+-------------------+
```
### Inheritance (IS-A)
**<|--** indicates an inheritance arrow

```md
+------------+      +---------------+       
| BaseClass  | <|-- | DerivedClass  |
+------------+      +---------------+
```
This means that **DerivedClass** inherite the **BaseClass**

### Inheritance Interface (IS-A)
**<|..** indicates an inheritance interface arrow

```md
+-----------------+      +---------------+
| InterfaceClass  | <|.. | ConcreteClass |
+-----------------+      +---------------+
```
This means that **ConcreteClass** inherite the **InterfaceClass** interface

### Association (HAS-A)
If you want to represent a usage or dependecy relationship where **ClassA** uses **ClassB** (but doesn't necessarily own it), you can use a simpler arrow notation.

```md
+----------+     +---------+
| ClassA   | --> | ClassB  |
+----------+     +---------+
```
It indicates a dependency such as through method calls or data references.

### Aggregation (HAS-A) (USE-IT)
**--o** indicates an Aggregation 
```md
+-----------------+          +-----------------+
|    ClassA       |          |     ClassB      |
|-----------------|          |-----------------|
|                 |o-------->|                 |
|                 |          |                 |
+-----------------+          +-----------------+
```
**ClassA** has an aggregetion relationship with **ClassB**
Aggregation is a weaker form of association where one class, (known as the whole), is associated with another class, (known as the part). The part can exist independently of the whole.

### Composition (HAS-A) (OWN-IT)
**<>--** indicates an Composition
```md
+-----------------+          +-----------------+
|    ClassA       |          |     ClassB      |
|-----------------|          |-----------------|
|                 |          |                 |
|                 |◇-------->|                 |
|                 |          |                 |
+-----------------+          +-----------------+
```
**ClassA** has an composition relationship with **ClassB**
Composition is a strong form of association where one class, (known as the whole or container), owns the other class, (known as the part or component).

