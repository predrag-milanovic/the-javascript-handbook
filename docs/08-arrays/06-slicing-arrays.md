# Slicing Arrays with `slice()`

The [`.slice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) method makes it easy to take a **portion** of an array without changing the original.

```js
const animals = ["ant", "bison", "camel", "duck", "elephant"]

console.log(animals.slice(2))
// ['camel', 'duck', 'elephant']

console.log(animals.slice(2, 4))
// ['camel', 'duck']

console.log(animals.slice(1, 5))
// ['bison', 'camel', 'duck', 'elephant']

console.log(animals.slice(-2))
// ['duck', 'elephant']

console.log(animals.slice(2, -1))
// ['camel', 'duck']

console.log(animals.slice())
// ['ant', 'bison', 'camel', 'duck', 'elephant']
```

---

## How `slice()` Works

`slice(start, end)` takes up to two arguments:

- `start`: the index where the slice begins (inclusive).
- `end`: the index where the slice stops (**exclusive**). The element at `end` is **not** included.

If you omit `end`, the slice goes from `start` all the way to the end of the array.

```js
const animals = ["ant", "bison", "camel", "duck", "elephant"]

animals.slice(2)    // ['camel', 'duck', 'elephant']
animals.slice(2, 4) // ['camel', 'duck']
```

`slice` does **not** modify the original array; it returns a **new** array with the selected elements.

---

## Using Negative Indexes

JavaScript arrays don’t support negative indexing directly (you can’t do `animals[-1]` to get the last element), but `slice` does accept **negative** indexes:

- A negative `start` or `end` is counted from the **end** of the array.

```js
const animals = ["ant", "bison", "camel", "duck", "elephant"]

animals.slice(-2)    // ['duck', 'elephant']
animals.slice(2, -1) // ['camel', 'duck']
```

This makes `slice` a handy tool for grabbing “from the end” segments or middle portions of an array without needing to calculate indexes manually.

