# Functions

As you might have guessed, JavaScript supports functions via the [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function) keyword.

Even JavaScript isn't crazy enough to not support functions.

```js
// function declaration
function getSum(a, b) {
	return a + b;
}

// function call
const result = getSum(60, 9);

console.log(result);
// 69
```

In this example, `getSum` is defined once and can be called multiple times with different arguments. Functions let you group reusable logic behind a name, making your code easier to read and maintain.

