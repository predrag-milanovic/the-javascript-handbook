# Immediate Invocation

You can immediately invoke a function right after defining it using the not-at-all-hard-to-pronounce acronym [**IIFE** (Immediately Invoked Function Expression)](https://developer.mozilla.org/en-US/docs/Glossary/IIFE).

```js
(function () {
	console.log("JavaScript: at least it's not Java");
})();
// JavaScript: at least it's not Java
```

Here, the function is defined as an expression (wrapped in parentheses) and then immediately called by the trailing `()`.

IIFEs can also return values and take arguments:

```js
const result = (function (a, b) {
	return a + b;
})(1, 2);

console.log(result);
// 3
```

The function is defined and then immediately executed. It looks a bit unusual at first, but it's occasionally useful for a few reasons:

- **Scope**: It creates its own local scope, so any variables declared inside don't leak into the outer scope.
- **Expression**: It can be convenient when you want to compute a value as a single expression (like the `result` example above).
- **Async**: It's a handy pattern for quickly running code in an async function without having to name it.

For example, you might see an async IIFE used to await something at the top level:

```js
(async function () {
	const response = await fetch("/api/data");
	const data = await response.json();
	console.log(data);
})();
```
