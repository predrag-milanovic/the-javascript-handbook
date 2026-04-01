# Getters and Setters

In JavaScript classes, getters and setters let you define special methods for reading and writing properties. They *look* like methods in the class body, but you *use* them like regular properties.

A getter is defined with the `get` keyword:

```js
class User {
	constructor(name, age) {
		this._name = name;
		this.age = age;
	}

	get name() {
		return this._name.toUpperCase();
	}
}

const predrag = new User("Predrag", 30);

console.log(predrag.name);
// PREDRAG
```

Notice how we renamed `this.name` to `this._name` in the constructor. This avoids a name collision between the `name` getter and the internal field that actually stores the value.

You *call* the getter like a property (`predrag.name`), but under the hood JavaScript is invoking the `get name()` function.

---

## Setters

Setters run whenever you assign to a property. They let you validate or transform values before storing them.

```js
class User {
	constructor(name, age) {
		this.name = name;
		this._age = age;
	}

	get age() {
		return this._age;
	}

	set age(value) {
		if (value < 0) {
			throw new Error("Age can't be negative.");
		}

		this._age = value;
	}
}

const predrag = new User("Predrag", 29);

predrag.age = -5;
// Error: Age can't be negative.

console.log(predrag.age);
// 29
```

Here the `set age(value)` method runs whenever `age` is assigned. If the value is invalid, it throws an error instead of silently accepting bad data.

---

## When to Use Them

Personally, I'm not a huge fan of getters and setters. When I read or assign a property, I usually expect a simple field access, not a hidden function call.

That said, they can be useful when:

- you need to validate input before saving it
- you want a computed value that still *looks* like a property
- you are integrating with APIs or frameworks that expect properties, not methods

Some patterns (for example, certain reactive state systems in front-end frameworks) make heavy use of getters and setters. My advice is to reach for them only when you **really** need this behavior. Most of the time, a plain method like `getAge()` or `setAge()` is simpler and more explicit.

