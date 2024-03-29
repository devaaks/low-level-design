# Decorator

Imagine you have a plain cake. Now, you want to add some decorations to make it look more appealing. The decorator design pattern works similarly in software development.

In easy language, the decorator pattern allows you to add new features or behaviors to objects without altering their structure. Just like adding decorations to a cake without changing the cake itself.

#### Real-World Analogy

Armies of most countries are structured as hierarchies. An army consists of several divisions; a division is a set of brigades, and a brigade consists of platoons, which can be broken down into squads. Finally, a squad is a small group of real soldiers. Orders are given at the top of the hierarchy and passed down onto each level until every soldier knows what needs to be done.

<details open>
<summary><b>Code</b></summary>

```typescript

// Step 1: Base Component
interface Pizza {
    getDescription(): string;
    cost(): number;
}

// Step 2: Concrete Component
class BasicPizza implements Pizza {
    getDescription(): string {
        return "Plain Pizza";
    }

    cost(): number {
        return 10; // Base cost of plain pizza
    }
}

// Step 3: Decorator
abstract class ToppingDecorator implements Pizza {
    protected pizza: Pizza;

    constructor(pizza: Pizza) {
        this.pizza = pizza;
    }

    getDescription(): string {
        return this.pizza.getDescription();
    }

    abstract cost(): number;
}

// Step 4: Concrete Decorators
class Cheese extends ToppingDecorator {
    cost(): number {
        return this.pizza.cost() + 2; // Additional cost of cheese
    }

    getDescription(): string {
        return this.pizza.getDescription() + ", Cheese";
    }
}

class Pepperoni extends ToppingDecorator {
    cost(): number {
        return this.pizza.cost() + 3; // Additional cost of pepperoni
    }

    getDescription(): string {
        return this.pizza.getDescription() + ", Pepperoni";
    }
}

```

#### Explanation:

1. **Base Component (Pizza)**: This interface defines the basic operations that all concrete pizza classes must implement. In our case, it has methods getDescription() to get the description of the pizza and cost() to get the cost of the pizza.

2. **Concrete Component (BasicPizza)**: This class represents a basic pizza. It implements the Pizza interface and provides the basic functionalities.

3. **Decorator (ToppingDecorator)**: This abstract class implements the Pizza interface and contains a reference to a Pizza object. It acts as a base class for concrete decorators.

4. **Concrete Decorators (Cheese, Pepperoni)**: These classes are concrete decorators that add specific toppings to the pizza. They extend the ToppingDecorator class, adding their own functionality (additional cost and description) on top of the decorated pizza.


```typescript

// Creating a plain pizza
let myPizza: Pizza = new BasicPizza();
console.log("Description:", myPizza.getDescription());
console.log("Cost:", myPizza.cost());

// Adding cheese topping
myPizza = new Cheese(myPizza);
console.log("Description:", myPizza.getDescription());
console.log("Cost:", myPizza.cost());

// Adding pepperoni topping
myPizza = new Pepperoni(myPizza);
console.log("Description:", myPizza.getDescription());
console.log("Cost:", myPizza.cost());

```

</details>

