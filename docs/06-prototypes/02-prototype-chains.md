Prototype Chains
=================

Every object has a prototype, and that prototype can in turn have its own prototype, creating a **prototype chain** that eventually goes back to the root [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) object. The prototype of `Object` is always `null`, which marks the end of the chain.

An object stores a reference to its prototype internally. You can read that prototype with [Object.getPrototypeOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf).

When we create a new plain object (a POJO: *plain old JavaScript object*), its prototype is automatically set to `Object.prototype`:

```js
const pureTitan = {
	name: "Eren's mom",
};

const beastTitan = Object.create(pureTitan);
beastTitan.name = "Zeke";

console.log(beastTitan); // { name: "Zeke" }
console.log(Object.getPrototypeOf(beastTitan)); // { name: "Eren's mom" }
console.log(Object.getPrototypeOf(Object.getPrototypeOf(beastTitan))); // {} (Object.prototype)
console.log(
	Object.getPrototypeOf(
		Object.getPrototypeOf(Object.getPrototypeOf(beastTitan)),
	),
); // null (end of the chain)
```

In this chain:

- `beastTitan`'s prototype is `pureTitan`.
- `pureTitan`'s prototype is `Object.prototype` (shown as `{}` here).
- `Object.prototype`'s prototype is `null`, so the lookup stops.

How Parent Members Are Found
----------------------------

You might think that using [`Object.create()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create) copies properties from the parent object onto the child object:

```js
const pureTitan = {
	name: "Eren's mom",
};

const beastTitan = Object.create(pureTitan);
console.log(beastTitan.name); // Eren's mom
```

But it does **not** copy anything. Instead, when you read a property, JavaScript walks the prototype chain.

When you access `beastTitan.name`, JavaScript:

1. Looks for `name` directly on `beastTitan`.
2. Doesn't find it, so it checks `Object.getPrototypeOf(beastTitan)`, which is `pureTitan`.
3. Finds `name` on `pureTitan` and uses that value.

This is the same lookup process described in the previous section: JavaScript keeps following the prototype chain until it either finds the property or hits `null`.

