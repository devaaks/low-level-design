# Factory Design Pattern

It provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.

**Example time -** 

Imagine you're running a pizza shop. You have different types of pizzas like cheese, pepperoni, and veggie. Customers come in and order pizzas. Now, think about how you create these pizzas.

In the Factory Method pattern:

1. You have a base interface or abstract class called `Pizza`.
2. Each type of `pizza` (cheese, pepperoni, veggie) is a subclass of `Pizza`.
3. You have a `PizzaFactory` class responsible for creating pizzas. It has a method like `createPizza(type)` which takes the type of pizza as input and returns the corresponding pizza object.
4. When a customer orders a pizza, you call `PizzaFactory.createPizza(type)` to get the specific type of pizza they want.

<br>

<details>
<summary><b>Code</b></summary>

```typescript
// Step 1: Define the Pizza interface or abstract class
interface Pizza {
    prepare(): void;
    bake(): void;
    cut(): void;
    box(): void;
}

// Step 2: Define subclasses for each type of pizza
class CheesePizza implements Pizza {
    prepare(): void {
        console.log("Preparing Cheese Pizza");
    }

    bake(): void {
        console.log("Baking Cheese Pizza");
    }

    cut(): void {
        console.log("Cutting Cheese Pizza");
    }

    box(): void {
        console.log("Boxing Cheese Pizza");
    }
}

class PepperoniPizza implements Pizza {
    prepare(): void {
        console.log("Preparing Pepperoni Pizza");
    }

    bake(): void {
        console.log("Baking Pepperoni Pizza");
    }

    cut(): void {
        console.log("Cutting Pepperoni Pizza");
    }

    box(): void {
        console.log("Boxing Pepperoni Pizza");
    }
}

// Step 3: Define the PizzaFactory class
class PizzaFactory {
    createPizza(type: string): Pizza {
        if (type === "cheese") {
            return new CheesePizza();
        } else if (type === "pepperoni") {
            return new PepperoniPizza();
        } else {
            throw new Error("Invalid pizza type");
        }
    }
}

// Step 4: Using the Factory Method to create pizzas
const factory = new PizzaFactory();
const pizza1 = factory.createPizza("cheese");
pizza1.prepare();  // Output: Preparing Cheese Pizza

const pizza2 = factory.createPizza("pepperoni");
pizza2.prepare();  // Output: Preparing Pepperoni Pizza
```

</details>

<br>

<details>

<summary><b>Benefits</b></summary>


The Factory Method pattern offers several benefits in software design:

1. **Encapsulation**: It encapsulates the object creation logic within the factory class. This means that the client code doesn't need to know how objects are created, only that they are created by the factory.

2. **Flexibility**: It allows for easy extension or modification of the object creation process. You can introduce new types of objects (in this case, pizzas) by simply adding new subclasses and modifying the factory method accordingly, without changing existing client code.

3. **Abstraction**: By using interfaces or abstract classes, the Factory Method pattern promotes programming to an interface rather than an implementation. This makes the system more flexible and easier to maintain.

4. **Centralized Control**: It centralizes the creation logic in one place (the factory class), making it easier to manage and maintain. Any changes or updates to the creation process can be made in a single location.

5. **Decoupling**: It decouples the client code from the concrete classes being instantiated. Clients interact with the factory interface, not directly with the concrete classes, which reduces dependencies and promotes loose coupling.

6. **Code Reusability**: It promotes code reusability by providing a mechanism for creating similar objects across different parts of an application. Once the factory is implemented, it can be reused to create objects wherever needed.

Overall, the Factory Method pattern enhances code maintainability, extensibility, and scalability by providing a structured way to create objects while hiding the details of instantiation from client code.

</details>
