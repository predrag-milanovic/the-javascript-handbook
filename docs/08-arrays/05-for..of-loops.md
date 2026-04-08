# For...of Loops

When you want to loop over every value in an array, JavaScript gives you a convenient [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) syntax. It lets you iterate a sequence **without** manually tracking an index counter.

Here’s the classic `for` loop over an array:

```js
const woods = ["oak", "pine", "maple"]

for (let i = 0; i < woods.length; i++) {
	console.log(woods[i])
}
// Prints:
// 'oak'
// 'pine'
// 'maple'
```

With `for...of`, you can loop directly over the values:

```js
const woods = ["oak", "pine", "maple"]

for (const wood of woods) {
	console.log(wood)
}
// Prints:
// 'oak'
// 'pine'
// 'maple'
```

This is shorter, easier to read, and you don’t have to worry about off‑by‑one errors or accessing the wrong index.

---

## `for...of` vs `for...in`

If you’ve used Python, `for...of` will feel similar to Python’s `for item in sequence:` style loops.

However, JavaScript also has a different construct called [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in), and it’s easy to confuse the two:

- `for...of` loops over **values** in an iterable (like an array).
- `for...in` loops over **keys** (property names), which for arrays are the **indexes** as strings.

Compare these two loops:

```js
const woods = ["oak", "pine", "maple"]

// for...in: loops over indexes (keys)
for (const index in woods) {
	console.log(index)
}
// Prints:
// '0'
// '1'
// '2'

// for...of: loops over values
for (const wood of woods) {
	console.log(wood)
}
// Prints:
// 'oak'
// 'pine'
// 'maple'
```

Use `for...of` when you want the actual values from an array (or other iterable). Reserve `for...in` for cases where you specifically need the keys or property names, such as iterating over the keys of a plain object.

