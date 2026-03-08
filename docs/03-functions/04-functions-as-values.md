# Functions as values

JavaScript supports [**first-class**](https://developer.mozilla.org/en-US/docs/Glossary/First-class_Function) and **higher-order** functions, which is just a fancy way of saying "functions are values". You can treat a function like any other value (such as a number or string): store it in a variable, pass it to another function, or return it from a function.

Let's start with two simple functions:

```js
function add(x, y) {
	return x + y;
}

function mul(x, y) {
	return x * y;
}
```

Both `add` and `mul` are regular functions, but we can also *use* them as values by passing them into another function.

## Passing a function as an argument

Here's a function that accepts another function as its fourth argument:

```js
function aggregate(a, b, c, arithmetic) {
	const firstResult = arithmetic(a, b);
	const secondResult = arithmetic(firstResult, c);
	return secondResult;
}
```

`arithmetic` is expected to be a function that takes two numbers and returns a number (like `add` or `mul`). `aggregate` uses it twice so it can work with three inputs instead of just two.

You can use it like this:

```js
function main() {
	const sum = aggregate(2, 3, 4, add);
	// sum is 9

	const product = aggregate(2, 3, 4, mul);
	// product is 24
}
```

Here, `add` and `mul` are passed *by name* (without parentheses) to `aggregate`. Inside `aggregate`, the `arithmetic` parameter is called like any other function. This is the core idea of functions as values and is the basis for many JavaScript features, such as callbacks and array methods like `map`, `filter`, and `reduce`.

