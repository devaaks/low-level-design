# Single Responsibility Principle

This principle states that a class should have only one reason to change, meaning it should have a single responsibility or job.

### Example
Think of a mobile phone. A mobile phone has multiple components like a camera, a touchscreen, a speaker, etc. Each of these components has its own distinct function. Applying SRP in code, you would create separate classes for each component rather than having a single class that handles all functionalities.

```java
// Before SRP
class MobilePhone {
    void makeCall() { /* ... */ }
    void takePhoto() { /* ... */ }
    void playMusic() { /* ... */ }
}

// After SRP
class Call {
    void makeCall() { /* ... */ }
}
class Camera {
    void takePhoto() { /* ... */ }
}

class MusicPlayer {
    void playMusic() { /* ... */ }
}
```