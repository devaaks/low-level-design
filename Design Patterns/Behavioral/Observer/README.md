# Observer

The observer pattern lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing. Basically, it's like having an event listener on a given object, and when that object performs the action we're listening for, we do something.

**Examples** 

1. React's useEffect hook might be a good example here. What useEffect does is execute a given function at the moment we declare.
2. Even plain old JavaScript event listeners can be thought of as observers.

<br>

<details open>
<summary><b>Code</b></summary>

```typescript
// Export a singleton Observer object, which contains a notify, subscribe, and unsubscribe method.
const observers = [];

export default Object.freeze({
  notify: (data) => observers.forEach((observer) => observer(data)),
  subscribe: (func) => observers.push(func),
  unsubscribe: (func) => {
    [...observers].forEach((observer, index) => {
      if (observer === func) {
        observers.splice(index, 1);
      }
    });
  },
});

// We can use this observable throughout the entire application, making it possible to subscribe functions to the observable
import Observable from "./observable";

function logger(data) {
  console.log(`${Date.now()} ${data}`);
}

Observable.subscribe(logger);

// Notify all subscribers based on certain events.
import Observable from "./observable";

document.getElementById("my-button").addEventListener("click", () => {
  Observable.notify("Clicked!"); // Notifies all subscribed observers
});

```

</details>

<br>

<details open>
<summary><b>Pros</b></summary>

**Separation of Concerns**: The observer objects aren't tightly coupled to the observable object, and can be (de)coupled at any time. The observable object is responsible for monitoring the events, while the observers simply handle the received data.

</details>

<details open>
<summary><b>Cons</b></summary>

**Decreased performance**: Notifying all subscribers might take a significant amount of time if the observer handling becomes too complex, or if there are too many subscibers to notify.

</details>


