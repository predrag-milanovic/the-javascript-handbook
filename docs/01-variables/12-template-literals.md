# Template literals

In JavaScript, [**template literals**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) are a convenient way to build strings that contain dynamic values.
They are similar in spirit to Python's f-strings.

Template literals:

- Use backticks `` ` `` instead of regular quotes.
- Let you embed JavaScript expressions using the `${ ... }` syntax.

```js
const shadeOfRed = 101;

console.log(`The shade is ${shadeOfRed}`);
// The shade is 101
```

Anything inside `${ ... }` is evaluated as normal JavaScript, and the result is then converted to a string and inserted into the surrounding text.

## Expressions inside `${}`

You are not limited to simple variable names inside `${}`.
Any valid JavaScript expression can go there: you can do math, call methods, or run logic checks directly inside the string.

```js
const price = 2.5;
const quantity = 3;
const item = "coffee";

console.log(`Total: $${price * quantity}`);
// Total: $7.5

console.log(`I need ${item.toUpperCase()}`);
// I need COFFEE
```

Because the expressions are evaluated at runtime, template literals are a powerful way to build readable strings that depend on your data and logic.

