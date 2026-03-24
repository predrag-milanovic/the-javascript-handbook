# Methods are not bound

In some languages (like Python or Go), methods are automatically **bound** to the instance they belong to. In JavaScript, methods are **not bound by default**. That means if you take a method off an object and use it as a standalone function (for example, as a callback), you can easily lose the original object context and break `this`.

## Losing `this` when extracting a method

Consider a simple object with a method that uses `this`:

```js
const user = {
	name: "Predrag",
	sayHi() {
		console.log(`Hi, my name is ${this.name}`);
	},
};

user.sayHi();
// Hi, my name is Predrag
```

When you call `user.sayHi()` directly, `this` inside `sayHi` points to the `user` object, so `this.name` works.

But if you **extract the method into a variable**, you lose that connection:

```js
const sayHi = user.sayHi;
sayHi();
// TypeError: Cannot read properties of undefined (reading 'name')
```

Here the function is called without any object on the left side, so in strict mode `this` is `undefined`, and accessing `this.name` throws an error.

## When methods are used as callbacks

This commonly happens when you pass a method as a **callback** to another function:

```js
const user = {
	firstName: "Predrag",
	lastName: "Milanovic",
	getFullName() {
		return `${this.firstName} ${this.lastName}`;
	},
};

function getGreeting(introduction, nameCallback) {
	return `${introduction}, ${nameCallback()}`;
}

console.log(user.getFullName());
// Predrag Milanovic

console.log(getGreeting("Hello", user.getFullName));
// TypeError: Cannot read properties of undefined (reading 'firstName')
```

Inside `getGreeting`, `nameCallback()` is called as a plain function, so its `this` is not `user` anymore. The method body expects `this.firstName` and `this.lastName`, but `this` is `undefined`, so it crashes.

## Fixing it with `bind`

If you want to safely use an object method as a callback, you need to **bind** it to the correct object first using [`Function.prototype.bind`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind).

```js
const boundGetFullName = user.getFullName.bind(user);

console.log(getGreeting("Hello", boundGetFullName));
// Hello, Predrag Milanovic
```

`bind` returns a **new function** where `this` is permanently set to the object you pass (`user` in this case). No matter how or where `boundGetFullName` is called, `this` inside it will always refer to `user`.

In practice, whenever you pass a method that relies on `this` into another function (for example, as a callback, event handler, or promise resolver), make sure it is either:

- Called directly as a method (like `user.getFullName()`), or
- Explicitly bound with `.bind(user)` before you pass it around.

