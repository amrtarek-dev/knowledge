Observer design pattern defines a one-to-many relationship between objects so that when one object changes state, all its dependents are notified and updated automatically.
## When
When changes in one object should trigger updates in other objects, but without tight coupling between them.
## Example Problem
A stock price monitoring system needs to notify multiple observers (like mobile apps or web applications) when a stock price changes.
## Solution
Implement an observer interface and a subject class that maintains a list of observers and notifies them of any state changes.
## OO Principles
- Loose Coupling (observers are decoupled from the subject)
- Open-Closed Principle (adding new observers does not require changes to the subject class)