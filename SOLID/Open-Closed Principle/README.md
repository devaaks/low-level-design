# Open/Closed Principle (OCP)

This principle suggests that classes should be open for extension but closed for modification. This means that you should be able to add new functionality without altering existing code.

Example: Consider a geometric shapes library. Instead of modifying the existing shape classes when adding new shapes, you could create a common interface for all shapes and extend that interface to create new shapes. This way, existing code remains unchanged while new shapes can be easily added.

## Example - 

```java
// Before OCP
class Circle {
    double radius;

    double area() {
        return Math.PI * radius * radius;
    }
}

// After OCP
interface Shape {
    double area();
}

class Circle implements Shape {
    double radius;

    @Override
    public double area() {
        return Math.PI * radius * radius;
    }
}

class Rectangle implements Shape {
    double width;
    double height;

    @Override
    public double area() {
        return width * height;
    }
}
```