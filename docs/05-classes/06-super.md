Super
=====

The [`super`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super) keyword lets a class call methods on its parent class. It is most commonly used in two places:

- Inside a child class constructor to call the parent constructor.
- Inside child methods to reuse or extend behavior defined in the parent.

Here's an example using Titans again:

```js
class Titan {
	constructor(name) {
		this.name = name;
	}

	toString() {
		return `Titan - Name: ${this.name}`;
	}
}

class BeastTitan extends Titan {
	constructor(name, power) {
		// call the parent's constructor
		super(name);
		this.power = power;
	}

	toString() {
		// call the parent's `toString` method
		return `${super.toString()}, Power: ${this.power}`;
	}
}

const beast = new BeastTitan("Zeke", 9000);
console.log(beast.toString());
// Titan - Name: Zeke, Power: 9000
```

In this example:

- `super(name)` in the `BeastTitan` constructor calls the `Titan` constructor so the `name` property is initialized by the parent.
- `super.toString()` inside the child `toString()` method calls the parent version and then adds extra information.

When a class uses `extends`, you must call `super()` before you can use `this` in the constructor. This ensures the parent part of the object is set up correctly before the child adds its own properties.

