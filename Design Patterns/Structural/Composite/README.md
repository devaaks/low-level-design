# Composite

Composite is a structural design pattern that lets you compose objects into tree structures and then work with these structures as if they were individual objects.

Composite pattern is used where we need to treat a group of objects in similar way as a single object. Composite pattern composes objects in term of a tree structure to represent part as well as whole hierarchy. This type of design pattern comes under structural pattern as this pattern creates a tree structure of group of objects.

#### Real-World Analogy

Armies of most countries are structured as hierarchies. An army consists of several divisions; a division is a set of brigades, and a brigade consists of platoons, which can be broken down into squads. Finally, a squad is a small group of real soldiers. Orders are given at the top of the hierarchy and passed down onto each level until every soldier knows what needs to be done.

<details open>
<summary><b>Code</b></summary>

```typescript

// Component interface
interface Graphic {
    draw(): void;
}

// Leaf class
class Line implements Graphic {
    draw(): void {
        console.log('Drawing a line');
    }
}

// Composite class
class Picture implements Graphic {
    private graphics: Graphic[] = [];

    add(graphic: Graphic): void {
        this.graphics.push(graphic);
    }

    draw(): void {
        console.log('Drawing a picture');
        this.graphics.forEach(graphic => {
            graphic.draw();
        });
    }
}

// Example usage
const line1 = new Line();
const line2 = new Line();
const picture = new Picture();
picture.add(line1);
picture.add(line2);

picture.draw();


```

</details>

