# Comparison operators

You’ve probably seen comparison operators in other languages already, and the basic inequalities work in JavaScript exactly as you’d expect:

```js
5 < 6;  // true
5 > 6;  // false
5 >= 6; // false
5 <= 6; // true
```

The interesting (and slightly weird) part in JavaScript is [equality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Equality_comparisons_and_sameness).

## Strict equality and inequality

To check whether two values are **exactly** the same, use **strict** equality and inequality:

```js
5 === 6; // false
5 !== 6; // true
```

- `===` ([strict equals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality)) compares both **value and type**.
- `!==` ([strict not equals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_inequality)) is the opposite: it’s `true` when value or type differ.

These are the operators you should reach for in almost all real-world JavaScript code.

## Loose equality and inequality

JavaScript also has **loose** equality operators that try to be “helpful” by converting types before comparing:

```js
5 == 6;   // false
5 == "5";  // true

5 != 6;   // true
5 != "5";  // false
```

- [`==`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality) and [`!=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality) perform **type coercion**: they may convert strings, numbers, booleans, and other values before comparing.
- Because of this, the string `"5"` and the number `5` are considered “equal” with `==`, which is usually **not** what you want in clean, predictable code.

This behavior is a fairly unique quirk of JavaScript. You can dive into the full rules for `==` if you’re curious, but for day-to-day development, it’s best to stick with `===` and `!==` and avoid `==` and `!=` entirely.

