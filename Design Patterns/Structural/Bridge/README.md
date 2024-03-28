# Bridge

Bridge is a structural design pattern that lets you split a large class or a set of closely related classes into two separate hierarchies—abstraction and implementation—which can be developed independently of each other.

<br>

Here's an explanation of the Bridge Pattern in TypeScript:

1. Abstraction: This is the high-level interface that clients interact with. It contains a reference to the Implementor and delegates the actual implementation to it. In TypeScript, this could be an abstract class or an interface.

2. Refined Abstraction: This is an extended abstraction that adds extra functionality on top of the basic abstraction. It still relies on the Implementor to perform its operations.

3. Implementor: This is the interface that defines the operations that concrete implementations must provide. In TypeScript, this could be an interface.

4. Concrete Implementor: This is the actual implementation of the Implementor interface. There can be multiple concrete implementations providing different ways to perform the operations defined by the Implementor interface.

<details>
<summary><b>Code</b></summary>

```typescript

// Implementor interface
interface DrawingAPI {
    drawCircle(x: number, y: number, radius: number): void;
}

// Concrete Implementor 1
class DrawingAPI1 implements DrawingAPI {
    drawCircle(x: number, y: number, radius: number): void {
        console.log(`API1.circle at ${x}:${y} with radius ${radius}`);
    }
}

// Concrete Implementor 2
class DrawingAPI2 implements DrawingAPI {
    drawCircle(x: number, y: number, radius: number): void {
        console.log(`API2.circle at ${x}:${y} with radius ${radius}`);
    }
}

// Abstraction
abstract class Shape {
    protected drawingAPI: DrawingAPI;

    constructor(drawingAPI: DrawingAPI) {
        this.drawingAPI = drawingAPI;
    }

    abstract draw(): void;
}

// Refined Abstraction
class Circle extends Shape {
    private x: number;
    private y: number;
    private radius: number;

    constructor(x: number, y: number, radius: number, drawingAPI: DrawingAPI) {
        super(drawingAPI);
        this.x = x;
        this.y = y;
        this.radius = radius;
    }

    draw(): void {
        this.drawingAPI.drawCircle(this.x, this.y, this.radius);
    }
}

// Usage
const circle1 = new Circle(1, 2, 3, new DrawingAPI1());
const circle2 = new Circle(5, 7, 11, new DrawingAPI2());

circle1.draw(); // Output: API1.circle at 1:2 with radius 3
circle2.draw(); // Output: API2.circle at 5:7 with radius 11

// In this example:
// DrawingAPI is the Implementor interface.
// DrawingAPI1 and DrawingAPI2 are the Concrete Implementors providing different ways to draw a circle.
// Shape is the Abstraction class, and Circle is the Refined Abstraction class. They delegate drawing to the Implementor interface (DrawingAPI).
// Circle can be created with different implementations of DrawingAPI, allowing the abstraction (Circle) and the implementation (DrawingAPI) to vary independently.

```

</details>
