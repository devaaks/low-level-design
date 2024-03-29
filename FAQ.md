# Abstract vs Interface

Here's a comparison between abstract classes and interfaces in a tabular format for better readability:

| Feature            | Abstract Class                                      | Interface                                     |
|--------------------|-----------------------------------------------------|-----------------------------------------------|
| What it is        | Blueprint for subclasses to inherit from            | Contract for classes to implement             |
| Methods            | Can have abstract (unimplemented) and concrete methods | All methods are abstract (no implementation) |
| Fields             | Can have variables (fields)                         | Cannot have variables (fields)               |
| Subclasses         | Subclasses must implement abstract methods          | Classes can implement multiple interfaces     |
| Default Behavior   | Can provide default method implementations         | Does not provide default implementations     |
| Instantiation      | Cannot be instantiated directly                     | Cannot be instantiated directly              |
