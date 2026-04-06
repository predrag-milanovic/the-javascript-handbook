# Array Spread

The [**`spread syntax (...)`**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) doesn’t just work with objects — you can also use it with arrays. It **expands** the elements of an existing array into individual values.

This is especially handy when you want to build a new array based on an existing one:

```js
const nums = [1, 2, 3]

const newNums = [...nums, 4, 5, 6]

console.log(newNums)
// Prints: [1, 2, 3, 4, 5, 6]
```

Here, `...nums` takes the three elements from `nums` and inserts them into `newNums`, followed by `4`, `5`, and `6`.

