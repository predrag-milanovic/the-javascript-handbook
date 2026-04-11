# Handling Errors

Errors are thrown (and should be thrown by you) when your code hits a non-happy path that it cannot or should not silently recover from.

Common examples include:

- Data received from an API is not in the expected format
- The connection to a database is lost
- A user tries to log in with an incorrect password

When an error is thrown, JavaScript immediately stops what it's doing in the current context and looks for the nearest [`try`/`catch`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch) block up the call stack. If it finds one, control jumps into the `catch` block. If it doesn't, the error crashes the program.

## Uncaught errors

Consider this code:

```js
const titan = {};
console.log(titan.neck.thickness);
console.log("done");
```

`titan.neck` is `undefined`, so trying to access `.thickness` throws a `TypeError`. The program prints something like:

```text
TypeError: Cannot read properties of undefined (reading 'thickness')
```

Execution stops there: it never reaches the `console.log("done")` line because the error is unhandled.

## Handling errors with try/catch

To prevent an error from crashing your program, you can wrap the potentially unsafe code in a `try`/`catch` block.

- Code inside the `try` block runs normally until an error is thrown.
- If an error happens, JavaScript jumps to the `catch` block, skipping any remaining lines in the `try`.

```js
try {
	const titan = {};
	console.log(titan.neck.thickness);
	console.log("what's a titan?");
} catch (err) {
	console.log(err.message);
}

console.log("done");
```

This prints:

```text
Cannot read properties of undefined (reading 'thickness')
done
```

The first line comes from `console.log(err.message)` in the `catch` block. The `err` variable holds the error object, and `message` is a human-readable description of what went wrong.

Because the error is caught and handled, the program continues running after the `try`/`catch` block and reaches the final `console.log("done")`.

