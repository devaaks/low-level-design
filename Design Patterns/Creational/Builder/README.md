# Builder

It is used to construct a complex object step by step. It allows the construction of a product in a step-by-step fashion, where the construction process can vary based on the type of product being built. The pattern separates the construction of a complex object from its representation, allowing the same construction process to create different representations.

### Components of the Builder Design Pattern

1. **Product**

    The Product is the complex object that the Builder pattern is responsible for constructing.

    It may consist of multiple components or parts, and its structure can vary based on the implementation.
    The Product is typically a class with attributes representing the different parts that the Builder constructs.

2. **Builder**

    The Builder is an interface or an abstract class that declares the construction steps for building a complex object.

    It typically includes methods for constructing individual parts of the product.
    By defining an interface, the Builder allows for the creation of different concrete builders that can produce variations of the product.

3. **ConcreteBuilder**

    ConcreteBuilder classes implement the Builder interface, providing specific implementations for building each part of the product.

    Each ConcreteBuilder is tailored to create a specific variation of the product.
    It keeps track of the product being constructed and provides methods for setting or constructing each part.

4. **Director**
    The Director is responsible for managing the construction process of the complex object.

    It collaborates with a Builder, but it doesn’t know the specific details about how each part of the object is constructed.
    It provides a high-level interface for constructing the product and managing the steps needed to create the complex object.

5. **Client**
    The Client is the code that initiates the construction of the complex object.

    It creates a Builder object and passes it to the Director to initiate the construction process.
    The Client may retrieve the final product from the Builder after construction is complete.

### Example

Suppose a user creates a document with a specific layout, fonts, and styling, and wishes to create similar documents with slight modifications.

Instead of starting from scratch each time, the user can use the Prototype pattern. The original document becomes the prototype, and new documents are created by cloning this prototype. This approach ensures that the new documents inherit the structure and styling of the original document while allowing for customization.

<p align="center">
  <img width="640" height="600" src="">
</p>

<br>

<details>
<summary><b>Code</b></summary>

```java
```
</details>

<br>

<details open>
<summary><b>Pros</b></summary>

</details>

<details open>
<summary><b>Cons</b></summary>

</details>
