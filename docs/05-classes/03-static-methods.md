# Static Methods

[Static](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/static) properties and methods belong to the **class itself**, not to individual instances of that class.

First, here’s a normal class with instance properties:

```js
class User {
	constructor(name, age) {
		this.name = name;
		this.age = age;
	}
}

const predrag = new User("Predrag", 30);
const allan = new User("Allan", 30);

console.log(predrag.name);
// predrag

console.log(allan.name);
// Allan
```

Here, `name` and `age` live on each instance (`predrag`, `allan`). They are *not* shared.

---

## Defining Static Members

Static members are declared with the `static` keyword and are accessed on the class, not on instances.

```js
class User {
	static numUsers = 0;

	constructor(name, age) {
		this.name = name;
		this.age = age;

		User.numUsers++;
	}

	static getNumUsers() {
		return User.numUsers;
	}
}

const predrag = new User("Predrag", 30);

console.log(User.getNumUsers());
// 1

const allan = new User("Allan", 30);

console.log(User.getNumUsers());
// 2
```

`numUsers` and `getNumUsers` belong to `User` the **class object**, not to `predrag` or `allan`.

Trying to call a static method on an instance doesn’t work:

```js
console.log(predrag.getNumUsers());
// TypeError: predrag.getNumUsers is not a function
```

---

## When to Use Static Methods

Because they are attached to the class itself, static methods are a good fit for:

- utility helpers closely related to the class
- factory methods (for example, `User.fromJSON(json)`)
- global-ish counters or registries (`User.numUsers`)

If you need per-instance data or behavior, stick with regular properties and methods instead.

