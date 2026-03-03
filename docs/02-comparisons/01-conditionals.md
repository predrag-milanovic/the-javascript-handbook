# Conditionals

In JavaScript, `if` statements use **parentheses** around the condition and **curly braces** around the block of code to run when the condition is true:

```js
if (height > 4) {
	console.log("You are tall enough!");
}
```

You can chain conditions with `else if` and provide a final fallback with `else`, just like in many other languages:

```js
if (height > 6) {
	console.log("You are super tall!");
} else if (height > 4) {
	console.log("You are tall enough!");
} else {
	console.log("You are not tall enough!");
}
```

Behind the scenes, these `if` and `else if` branches rely on comparison operators to produce `true` or `false`.

Common ones you’ll see all the time:

- `===` – equal to
- `!==` – not equal to
- `<` – less than
- `>` – greater than
- `<=` – less than or equal to
- `>=` – greater than or equal to
