# Numbers

In some languages (like Python), whole numbers are **integers** and numbers with decimal parts are **floats**—two different types.

In JavaScript, things are simpler: almost all numeric values share the same type, called **number**.

```js
let x = 2      // number
x = 5.69       // also a number
x = -5.42      // still a number
```

Numbers are **not** surrounded by quotes when you create them. If you put them in quotes, they become strings instead.

---

## Basic arithmetic

You can do arithmetic with numbers just as you’d expect.

```js
let sum = 2 + 3 + 7       // 12
let difference = 5.3 - 2.1 // 3.2
let product = 2 * 3        // 6
let quotient = 6 / 2       // 3
```

Here are the core operations:

```js
2 + 1  // 3   (addition)
2 - 1  // 1   (subtraction)
2 * 2  // 4   (multiplication)
3 / 2  // 1.5 (division)
```

Notice that `3 / 2` gives `1.5`. That’s still just a **number**—JavaScript doesn’t switch to a special “float” type.
