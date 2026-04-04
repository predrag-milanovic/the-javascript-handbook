While
=====

Like many other languages, JavaScript has a [`while`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while) loop. It keeps running **as long as its condition is `true`**.

```js
const jane = {
	name: "Jane",
	mom: {
		name: "Alice",
		mom: {
			name: "Lilly",
			mom: {
				name: "Granny",
			},
		},
	},
};

let currentPerson = jane;
while (currentPerson) {
	console.log(currentPerson.name);
	currentPerson = currentPerson.mom;
}
console.log("No more ancestors!");
// Jane
// Alice
// Lilly
// Granny
// No more ancestors!
```

Here's what happens in this example:

- The `while` condition is `currentPerson`, which is treated as a boolean.
- As long as `currentPerson` is an object (a "truthy" value), the loop body runs.
- Inside the loop, the code logs the current person's name and then moves up one generation (`currentPerson = currentPerson.mom`).
- When `currentPerson` finally becomes `undefined` (no more `mom`), the condition is `false` and the loop stops.

`while` loops are useful when you don't know in advance how many times you'll need to repeat something—you just keep going until a condition becomes `false`.

