# Includes

Checking whether a value exists in an array is really easy in JavaScript — just use the [`.includes()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes) method.

```js
const fruits = ["apple", "orange", "banana"]

console.log(fruits.includes("orange"))
// Prints: true

console.log(fruits.includes("pear"))
// Prints: false
```

The `includes` method returns `true` if the element is found in the array, and `false` otherwise.

---

## `includes` on Strings

Strings also have an [`includes`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes) method that checks whether a substring appears inside a larger string:

```js
const str = "Hello, world!"

console.log(str.includes("world"))
// Prints: true

console.log(str.includes("banana"))
// Prints: false
```

This is often more readable than using older methods like `indexOf`.

