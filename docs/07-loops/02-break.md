Break
=====

The [`break`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break) keyword lets you exit a loop early.

```js
for (let i = 0; i < 10; i++) {
	if (i === 3) {
		break;
	}
	console.log(i);
}
// Prints:
// 0
// 1
// 2
```

As soon as JavaScript hits `break`, it **immediately** exits the loop, even if the loop condition (`i < 10`) is still `true`.

You can also omit the loop condition to create an intentional infinite loop, then use `break` to exit when you're ready:

```js
for (let i = 0; ; i++) {
	if (i === 3) {
		break;
	}
	console.log(i);
}
// 0
// 1
// 2
```

In both examples, the moment a `break` statement runs, control jumps out of the loop and continues with the next statement after the loop, regardless of what the loop condition is.

