# Passing by Value

In JavaScript, primitive values (like numbers, strings, and booleans) are passed to functions **by value**. That means the function receives a copy of the value, not the original itself. Changing the parameter inside the function does not change the variable that was passed in.

> Objects and arrays behave differently (they effectively work through references). We'll talk about them later.

```js
let x = 5;

increment(x);

console.log(x);
// 5

function increment(x) {
	x++;
	console.log(x);
	// 6
}
```

Here, `increment` receives a copy of `x`. Incrementing that copy does not affect the original `x` in the outer scope, so it stays `5` after the function call.

