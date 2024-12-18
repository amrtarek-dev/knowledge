Factory Method design pattern provides an interface for creating objects in a superclass but allows subclasses to alter the type of objects that will be created.

## When
When the exact types of objects needed are not known until runtime or when dealing with multiple related classes.

## Example problem
An application needs to create different types of buttons (e.g., WindowsButton, MacButton) but doesn’t know which until runtime.

## Solution
Create a factory method in a superclass that subclasses can override to create specific object instances.

## OO Principles
- Dependency Inversion Principle (high-level classes should not depend on low-level classes)
- Open-Closed Principle (adding new products does not require modifying the existing code)