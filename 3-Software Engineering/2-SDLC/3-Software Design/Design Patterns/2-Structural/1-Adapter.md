Adapter design pattern allows incompatible interfaces to work together.
## When
When you need to integrate existing classes with a new interface without modifying the existing code.
## Example Problem
You have a legacy system that provides output in XML, but you need JSON in your new system.
## Solution
Implement an adapter that converts the interface of the legacy system into the desired format (e.g., wrapping XML outputs into JSON).
## OO Principles
- Interface Segregation Principle (breaking down interfaces into smaller, more specific ones)
- Single Responsibility Principle (the adapter class handles the responsibility of translating between interfaces)