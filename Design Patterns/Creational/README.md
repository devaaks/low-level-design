# Creational Design Patterns

It deal with object creation mechanisms, attempting to create objects in a manner suitable to the situation. They provide flexibility in object creation by abstracting the process away from the client and the system.

These patterns primarily focus on how objects are instantiated or created, ensuring that the process is flexible, efficient, and easy to maintain. Creational patterns typically encapsulate the knowledge about which classes to instantiate and how to instantiate them.

### Common Creational Design Patterns

1. **Singleton Pattern**: Ensures that a class has only one instance and provides a global point of access to that instance.

2. **Factory Method Pattern**: Defines an interface for creating an object but allows subclasses to alter the type of objects that will be created.

3. **Abstract Factory Pattern**: Provides an interface for creating families of related or dependent objects without specifying their concrete classes.

4. **Builder Pattern**: Separates the construction of a complex object from its representation, allowing the same construction process to create different representations.

5. **Prototype Pattern**: Creates new objects by copying an existing object, known as a prototype, through cloning.

6. **Lazy Initialization**: Delays the creation of an object or the computation of a value until it is first accessed.

7. **Object Pool Pattern**: Manages a pool of reusable objects for use by clients, instead of creating new objects each time.

8. **Dependency Injection (DI) Pattern**: Provides a technique for supplying external dependencies to an object, rather than creating them internally, promoting loose coupling and easier testing.

These patterns help improve code flexibility, reusability, and maintainability by providing various strategies for object creation. They enable developers to adapt the creation process based on changing requirements and conditions, while also promoting good design practices such as encapsulation and separation of concerns.
