# Methods can mutate objects

Object methods don’t just *read* data – they can also **change** (mutate) the object they belong to.

```js
const tree = {
	height: 256,
	color: "green",
	cut() {
		this.height /= 2;
	},
};

tree.cut();
console.log(tree.height);
// prints 128

tree.cut();
console.log(tree.height);
// prints 64
```

Each time we call `tree.cut()`, the method updates `tree.height` in place by using `this` to refer to the same `tree` object.

You might be wondering:

> Wait… I thought `tree` was a constant?!

In JavaScript, `const` does **not** make the contents of an object immutable. It only means you can’t reassign the *variable* to a different value:

```js
const tree = { height: 256 };

tree.height = 128; // ✅ allowed – we’re mutating the existing object

tree = { height: 64 }; // ❌ TypeError – can’t reassign a const variable
```

So `const` protects the *binding*, not the *inside* of the object. Methods on a `const` object can still freely mutate its properties. If you need truly immutable data, you have to enforce that by convention or by using libraries and patterns designed for immutability.

