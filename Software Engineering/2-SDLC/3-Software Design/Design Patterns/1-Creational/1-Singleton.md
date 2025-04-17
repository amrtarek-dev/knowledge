Singleton design pattern ensures that a class has only one instance and provides a global point of access to it.

## When
When only one instance of a class is needed, like a database connection or configuration file.

## Example problem
You want to control access to shared resources (like logging or configurations) across an application.

## Solution
Implement a class that creates and manages only one instance of itself and ensures that other classes can access this instance.

## OO Principles
- Encapsulation (providing controlled access to the instance)
- Single Responsibility Principle (ensuring the class is responsible for managing its instance)