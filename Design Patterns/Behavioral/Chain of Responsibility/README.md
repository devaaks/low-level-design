# Chain of Responsibility

The Chain of Responsibility passes requests along a chain of handlers. Each handler decides either to process the request or to pass it to the next handler in the chain.

This pattern is mainly used to introduce loose coupling to the application. It decouples the sender and receiver of a particular request based on the type.

![Screenshot 2024-03-26 at 11 53 04 PM](https://github.com/devaaks/low-level-design/assets/16061289/80634f73-1463-466d-ba74-437977160aa3)

**Examples** 

Middlewares in Express are somehow handlers that either process a request or pass it to the next handler.

**Usage**

1. When the program processes different kinds of requests in various ways but sequences are unknown beforehand.
2. When there is a requirement to execute several handlers in a particular order.
3. When the sequence of handlers changes at runtime.

<details open>
<summary><b>Code</b></summary>

```javascript

const Request = function (amount) {
    this.amount = amount;
    console.log("Requested: $" + amount + "\n");
}

Request.prototype = {
    get: function (bill) {
        const count = Math.floor(this.amount / bill);
        this.amount -= count * bill;
        console.log("Dispense " + count + " $" + bill + " bills");
        return this;
    }
}
function run() {
    const request = new Request(378);

    request.get(100).get(50).get(20).get(10).get(5).get(1);
}

```

</details>

<br>

<details open>
<summary><b>Pros</b></summary>

1. Possibility to control the order of request handling.
2. Introduce new handlers into the application without breaking the existing code.
3. Decoupling of classes(Operations invoking and performing.

</details>

<details open>
<summary><b>Cons</b></summary>

1. Possibility of having unhandled requests.
2. Possibility of the end-user to manipulate the application.

</details>
