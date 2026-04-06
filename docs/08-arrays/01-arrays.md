# Arrays

In JavaScript, an [**array**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) is an ordered collection of values. If you are familiar with Python, you can think of JavaScript arrays as very similar to Python’s lists.

One important characteristic of JavaScript arrays is that the items **do not need to be of the same type**. JavaScript is dynamically and loosely typed, so a single array can hold numbers, strings, booleans, and more — all together:

```js
const numbers = [1, 2, 3, 4, 5]
const strings = ["banana", "apple", "pear"]
const miscellaneous = [true, 7, "adamantium"]
```

---

## Accessing Items by Index

You access items in an array using **zero-based indexing** and square brackets `[]`. The first element is at index `0`, the second at `1`, and so on:

```js
const strings = ["banana", "apple", "pear"]

console.log(strings[0])
// Prints: 'banana'

console.log(strings[2])
// Prints: 'pear'
```

If you try to access an index that doesn’t exist, you’ll get `undefined`.

---

## Adding Items with `push()`

You can add new items to the **end** of an array using the [`push`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push) method:

```js
const drinks = []

drinks.push("lemonade")
console.log(drinks)
// Prints: ['lemonade']

drinks.push("root beer")
console.log(drinks)
// Prints: ['lemonade', 'root beer']
```

Under the hood, `push` adds the new value at the next available index and updates the array’s `length`.
