# Liskov Substitution Principle

This principle emphasizes that objects of derived classes should be able to replace objects of their base classes without affecting the correctness of the program.

## Key Points:
* It states that replacing an instance of a class with its child class should not produce any negative side effects or break the existing codebase.
* Subclasses can modify or override parent class methods but should not change method signatures, introduce new functions not present in the parent class, or modify the parent class itself.

## Benefits:
* Preventing Codebase Breakage: By adhering to LSP, developers can extend existing code with new classes without fear of breaking the existing functionality.
* Maintainability: LSP promotes code that is easier to maintain and extend by ensuring that subclasses can be used seamlessly in place of their base classes.
* Scalability: It helps in creating flexible and loosely-coupled classes, making it easier to handle changing requirements and add new functionalities.

### Example
Imagine a scenario where you have a base class “Bird” and derived classes “Sparrow” and “Ostrich”. If you follow LSP, you should be able to use any instance of a derived class (e.g., “Sparrow”) wherever an instance of the base class (“Bird”) is expected, without causing unexpected behavior.

```java
class Bird {
    void fly() { /* ... */ }
}

class Sparrow extends Bird {
    @Override
    void fly() { /* ... */ }
}

class Ostrich extends Bird {
    // This class doesn't override fly()
}
```