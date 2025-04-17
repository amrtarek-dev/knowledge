Composite design pattern allows you to compose objects into tree-like structures to represent part-whole hierarchies.
## When
When individual objects and groups of objects need to be treated the same way.
## Example Problem
You have a menu structure where individual menu items and submenus should be treated uniformly.
## Solution
Implement a class hierarchy where both individual items and groups of items (composites) inherit from the same base class.
## OO Principles
- Liskov Substitution Principle (objects should be replaceable with instances of their subtypes)
- Open-Closed Principle (the system can be extended with new menu items or structures without modifying existing code)