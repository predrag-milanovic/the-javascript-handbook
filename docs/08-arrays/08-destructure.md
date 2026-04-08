# Destructuring Arrays

You can [**destructure**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring) an array just like you can an object. Destructuring lets you pull values out of an array and assign them to variables in a single, compact expression.

```js
const nums = [1, 2, 3]

function double([a, b, c]) {
	return [a * 2, b * 2, c * 2]
}

const [x, y, z] = double(nums)
console.log(x, y, z)
// Prints: 2 4 6
```

---

## Destructuring the First Elements

If you only care about the first element, you can destructure just that:

```js
const nums = [1, 2, 3]

const [x] = double(nums)
console.log(x)
// Prints: 2
```

You can also skip elements by leaving “holes” in the pattern:

```js
const [first, , third] = double(nums)
// first = 2, third = 6
```

---

## Using the Rest Operator

If you are not sure how many elements there are, you can use the **rest operator** `...` to capture the remaining elements into a new array:

```js
const nums = [1, 2, 3]

const [x, ...theRestOfThem] = double(nums)
console.log(x)
// Prints: 2

console.log(theRestOfThem)
// Prints: [4, 6]
```

The variable created with `...` is always an array. If there are no remaining elements, it will simply be an empty array `[]`:

```js
const [x, y, z, ...a] = double(nums)
console.log(x, y, z, a)
// Prints: 2 4 6 []
```

---

## Over‑Destructuring

If you destructure more variables than there are elements in the array, the extra variables will be set to `undefined`:

```js
const nums = [1, 2, 3]

const [x, y, z, a] = double(nums)
console.log(x, y, z, typeof a)
// Prints: 2 4 6 'undefined'
```

This behavior is normal and can be useful when you only care about the first few values and want the rest (if any) to default to `undefined`.

