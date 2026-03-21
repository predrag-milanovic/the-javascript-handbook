# Returning objects from functions

In JavaScript a function can only return **one value**. When you want to give back multiple pieces of data, a very common pattern is to return **a single object** that groups those values together.

## Grouping multiple results

Here’s a function that performs several calculations at once and returns them in an object:

```js
function doAllTheMath(x, y) {
	const sum = x + y;
	const difference = x - y;
	const product = x * y;
	const quotient = x / y;

	return {
		sum,
		difference,
		product,
		quotient,
	};
}

const results = doAllTheMath(10, 5);

console.log(results.sum);
// 15
console.log(results.difference);
// 5
console.log(results.product);
// 50
console.log(results.quotient);
// 2
```

The object keys (`sum`, `difference`, `product`, `quotient`) act as clear labels for each returned value, which makes the code easier to read and less error‑prone than returning an array and remembering positions like `result[0]`, `result[1]`, and so on.

