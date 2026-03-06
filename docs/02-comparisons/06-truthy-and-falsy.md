## Truthy and Falsy

In JavaScript, values are often used in a *Boolean context* (for example, inside `if`, `while`, the ternary operator, or logical operators like `&&` and `||`). In these contexts, a value is automatically coerced to either `true` or `false`.

- [**Truthy**](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) values are treated as `true` in a Boolean context.
- [**Falsy**](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) values are treated as `false` in a Boolean context.

You usually don't need to convert values to `true`/`false` explicitly; JavaScript does it for you:

```js
if ("hello") {
	console.log("'hello' is truthy");
}

if (42) {
	console.log("42 is truthy");
}

// 'hello' is truthy
// 42 is truthy
```

Here, the non-empty string `"hello"` and the non-zero number `42` are both truthy, so the `if` blocks run.

### Falsy values

"Falsy" values work the same way, but they are treated as `false` when coerced to a Boolean. If the value is falsy, the `if` block will **not** run:

```js
if (0) {
	console.log("0 is falsy");
}

if (null) {
	console.log("null is falsy");
}

if (undefined) {
	console.log("undefined is falsy");
}

// none of the console.log calls run
```

In JavaScript there are only a handful of falsy values. **Everything else is truthy.**

### Common truthy values

Examples of values that are truthy:

- `true`
- Any non-zero number, e.g. `42`, `-1`, `3.14`
- Any non-empty string, e.g. `"hello"`, `"0"`, `"false"`
- `[]` (an empty array)
- `{}` (an empty object)
- `function () {}` (a function, even if it does nothing)

### Common falsy values

These values are falsy in JavaScript:

- `false`
- `0` and `-0`
- `""` (empty string)
- `null`
- `undefined`
- `NaN` (Not-a-Number)

Remember: if a value is **not** in the falsy list above, it will be treated as truthy.

This behavior is very common in idiomatic JavaScript, for example:

```js
const name = "";

if (!name) {
	console.log("Please provide a name");
}
```

Because `""` is falsy, the `if` condition passes and the message is logged.

