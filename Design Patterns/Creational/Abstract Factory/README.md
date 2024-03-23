# Abstract Factory

It is a creational design pattern that provides an interface for creating families of related or dependent objects without specifying their concrete classes.

In other words, it allows you to create objects without specifying their exact type. Instead, it defines an interface (or abstract class) for creating families of related objects, and concrete implementations of this interface produce objects of specific types.

<br>

<details>
<summary><b>Code</b></summary>

```typescript
// Abstract Product: Computer
interface Computer {
    specs(): string;
}

// Concrete Products: Laptop and Desktop
class Laptop implements Computer {
    constructor(private processor: string, private ram: string, private storage: string) {}

    specs(): string {
        return `Laptop: ${this.processor}, ${this.ram}, ${this.storage}`;
    }
}

class Desktop implements Computer {
    constructor(private processor: string, private ram: string, private storage: string) {}

    specs(): string {
        return `Desktop: ${this.processor}, ${this.ram}, ${this.storage}`;
    }
}

// Abstract Factory Interface
interface ComputerFactory {
    createComputer(): Computer;
}

// Concrete Factories: LaptopFactory and DesktopFactory
class LaptopFactory implements ComputerFactory {
    createComputer(): Computer {
        return new Laptop("Intel i7", "16GB", "512GB SSD");
    }
}

class DesktopFactory implements ComputerFactory {
    createComputer(): Computer {
        return new Desktop("AMD Ryzen 9", "32GB", "1TB HDD");
    }
}

// Client Code
function buildComputer(factory: ComputerFactory): void {
    const computer = factory.createComputer();
    console.log("Built a", computer.specs());
}

// Usage
const laptopFactory = new LaptopFactory();
const desktopFactory = new DesktopFactory();

buildComputer(laptopFactory);  // Output: Built a Laptop: Intel i7, 16GB, 512GB SSD
buildComputer(desktopFactory); // Output: Built a Desktop: AMD Ryzen 9, 32GB, 1TB HDD

```

</details>

<br>

<details open>
<summary><b>Pros</b></summary>

1. You can be sure that the products you’re getting from a factory are compatible with each other.
2. You avoid tight coupling between concrete products and client code.
3. Single Responsibility Principle. You can extract the product creation code into one place, making the code easier to support.
4. Open/Closed Principle. You can introduce new variants of products without breaking existing client code.


</details>


<details open>
<summary><b>Cons</b></summary>

The code may become more complicated than it should be, since a lot of new interfaces and classes are introduced along with the pattern.

</details>
