## Nullish Coalescing (`??`)

On the web, values are often missing, not yet loaded, or explicitly empty. A lot of JavaScript exists just to handle cases where something might be `null` or `undefined`.

The [**nullish coalescing operator** `??`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing) is a concise way to provide a default value only when a value is actually *nullish* (that is, `null` or `undefined`).

```js
let myName = null;

console.log(myName ?? "Anonymous"); // "Anonymous"

myName = "Predrag";

console.log(myName ?? "Anonymous"); // "Predrag"
```

The rule is:

- If the value on the **left** of `??` is `null` or `undefined`, return the value on the **right**.
- Otherwise, return the value on the **left`** unchanged.

This makes it easy to set sensible defaults for values that might be missing:

```js
const userProvidedTheme = undefined;
const theme = userProvidedTheme ?? "light";

// theme is "light" because userProvidedTheme is undefined
```

Unlike the logical OR operator `||`, `??` does **not** treat other falsy values (like `0`, `""`, or `false`) as empty. It only falls back when the value is `null` or `undefined`.

