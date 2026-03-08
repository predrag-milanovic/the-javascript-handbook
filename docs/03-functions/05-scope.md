# Scope

[Scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope) in JavaScript defines *where* variables and functions are accessible in your code. Different environments (like the browser or [Node.js](https://en.wikipedia.org/wiki/Node.js)) expose different "outer" scopes, but the basic idea is always the same: where was this variable declared, and from which code can I use it?

You can think of scope in a few main levels, from widest to most narrow.

## Global scope

Variables in the global scope can be accessed from anywhere in your program.

- In browsers, global variables become properties of the `window` object.

	```js
	window.myGlobalVar = "hello world";

	console.log(myGlobalVar); // "hello world"
	console.log(window.myGlobalVar); // "hello world"
	```

- In Node.js, the global object is called `global` instead of `window`.

	```js
	global.myGlobalVar = "hello world";

	console.log(global.myGlobalVar); // "hello world"
	```

Globals are convenient but can easily cause name clashes and hard-to-track bugs, so it's usually better to keep variables in smaller scopes.

## Module scope

In ES modules (both in Node.js and modern browsers), any variables declared at the top level of a module are scoped to that module, not to the global object.

```js
// in some-module.js
const secret = "not global";

console.log(secret); // works here
```

If you want other modules to use a value, you must explicitly export it:

```js
// some-module.js
export const answer = 42;

// main.js
import { answer } from "./some-module.js";

console.log(answer); // 42
```

In the browser, using `<script type="module">` creates this module scope; top-level `const`, `let`, and `class` declarations are not added to `window`.

## Function scope

Functions create their own scope. Variables declared inside a function are only visible inside that function (and any nested functions).

Older JavaScript relied heavily on `var`, which is limited to the *function* scope:

```js
function example() {
	var message = "hello";
	console.log(message); // "hello"
}

console.log(message); // ReferenceError: message is not defined
```

## Block scope

[ES6](https://en.wikipedia.org/wiki/ECMAScript) introduced block scope with the `let` and `const` keywords. A *block* is anything inside curly braces `{}`—for example, an `if` statement or a loop.

```js
if (true) {
	const value = 123;
	console.log(value); // 123
}

console.log(value); // ReferenceError: value is not defined
```

Variables declared with `let` and `const` exist only inside their block. This makes code more predictable and avoids many of the surprising behaviors of `var` (like accidental hoisting and leaking variables out of loops).

Understanding how scope works is key to reasoning about where your data lives, avoiding bugs, and writing more modular, maintainable JavaScript.

