# Interface Segregation Principle

This principle states that clients should not be forced to depend on interfaces they do not use. In other words, keep interfaces small and focused.

### Example
In a messaging application, you might have interfaces for sending, receiving, and displaying messages. Instead of having a single large interface for all messaging operations, you would split it into smaller interfaces so that classes only need to implement the methods relevant to them.

```java
// Before ISP
interface Messaging {
    void send();
    void receive();
    void display();
}

// After ISP
interface Sender {
    void send();
}

interface Receiver {
    void receive();
}

interface Displayable {
    void display();
}
```