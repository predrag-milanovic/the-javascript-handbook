## The `finally` block

In addition to `try` and `catch`, JavaScript error handling also supports a [`finally` block](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch#syntax).

The code inside `finally` runs *every time* the `try`/`catch` construct finishes, regardless of whether an error was thrown or caught.

Use `finally` when you need to run cleanup or finishing logic no matter what happens in the `try` or `catch` blocks.

For example:

```js
try {
	const titan = {};
	console.log(titan.neck.thickness);
	console.log("what's a titan?");
} catch (err) {
	console.log(err.message);
} finally {
	console.log("This will always run regardless of any errors.");
}
```

Output:

```text
Cannot read properties of undefined (reading 'thickness')
This will always run regardless of any errors.
```

Even if something goes wrong *inside* the `catch` block (for example, another error is thrown there), the `finally` block still runs before control flow leaves the entire `try`/`catch`/`finally` construct.

