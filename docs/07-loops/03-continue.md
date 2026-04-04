Continue
========

The [`continue`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue) keyword **skips the rest of the current loop iteration** and moves on to the next one.

```js
for (let i = 0; i < 10; i++) {
	if (i % 2 === 0) {
		continue;
	}
	console.log(i);
}
// Prints:
// 1
// 3
// 5
// 7
// 9
```

Here's what happens in this example:

- When `i` is even (`0, 2, 4, 6, 8`), the `if` condition is `true`, so `continue` runs.
- JavaScript **skips** `console.log(i)` for that iteration and jumps straight to the next `i`.
- When `i` is odd (`1, 3, 5, 7, 9`), the `if` is `false`, so `continue` does not run and the number is logged.

Unlike `break`, which exits the loop entirely, `continue` keeps the loop going—it just skips whatever code comes after it in the current iteration.

