# The `this` keyword

The [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) keyword is one of the most confusing parts of JavaScript. Once you see the main patterns it’s manageable, but it’s definitely not intuitive.

Roughly speaking, `this` refers to the **context where a piece of code is executed**. That context depends on *how* and *where* the code runs.

## Global context

In non–strict mode, at the top level:

- In a **browser**, `this` refers to the global [`window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) object.
- In **Node.js modules**, `this` is the module’s export object (often `{}`), **not** the global object.

```js
// in a browser
console.log(this);
// Window { ... }

// in Node.js (inside a module)
console.log(this);
// {}
```

## Strict mode

In [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode), `this` in the global scope is `undefined` in both browsers and Node.js.

```js
"use strict";
console.log(typeof this);
// "undefined"
```

## Method context

Inside a **regular [method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions)** or a [**constructor**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new), `this` usually refers to the object the method is called on.

```js
const myObject = {
	message: "Hello, World!",
	myMethod() {
		console.log(this);
		console.log(this.message);
	},
};

myObject.myMethod();
// { message: "Hello, World!", myMethod: [Function: myMethod] }
// "Hello, World!"
```

Here `this` inside `myMethod` points to `myObject`, so `this.message` reads the `message` property from the same object.
