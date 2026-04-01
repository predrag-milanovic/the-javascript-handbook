# Classes

[Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) in JavaScript are templates for creating objects. Unlike some languages, you don't *need* classes to make objects in JavaScript, but they can make your code more organized and readable when you’re modeling things like users, products, or movies.

Here’s a simple class:

```js
class User {
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}
}

const user = new User("Predrag", 100);
```

---

## How It Works

- The [**class declaration**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/class) `class User { ... }` defines a new class.
- The [**`constructor` method**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/constructor) is a special method that runs when you create a new instance.
- The [**`new` keyword**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) calls the constructor and returns a new object.

In the example above:

- `new User("Predrag", 100)` creates a new object.
- Inside the constructor, `this.name` and `this.age` are set on that new object.

You can create as many `User` instances as you like, each with its own `name` and `age`. Later chapters in this section will build on this with private properties, static methods, and getters/setters.

