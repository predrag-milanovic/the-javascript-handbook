## Null vs. undefined

If you’re coming from a language like Python, you might think:

> "Ah, so `undefined` is like `None`. Easy."

Yes… but also no. One of JavaScript’s more confusing features is that it has **two** values for "nothing":

- [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined): the value is missing or not set yet ("very nothing")
- [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null): the value is explicitly set to "no value" ("kinda nothing")

### `undefined`: the default "no value"

`undefined` is what you get by default when a variable exists but hasn’t been given a value yet:

```js
let myName;

console.log(myName); // undefined
```

In many codebases, `undefined` is used anywhere you’d use `None` in Python or `nil` in Go.

### `null`: explicitly "empty"

To get `null`, you must assign it yourself:

```js
let myName = null;

console.log(myName); // null
```

Developers often use `null` to signal an *intentional* "no value" state, for example when a value will be filled in later or when something is known to be empty.

### `typeof null`

There’s a long-standing quirk in JavaScript:

```js
console.log(typeof null); // "object"
```

According to the [ECMAScript specification](https://tc39.es/ecma262/#sec-ecmascript-language-types), `null` is its own primitive type, not an object. The `"object"` result from `typeof` is a historical bug that can’t be fixed without breaking a lot of existing code.

### Which should you use?

In many situations, `null` and `undefined` behave similarly, but it’s important to be consistent in your own codebase and understand the difference:

- Use `undefined` for values that are simply "not set yet" or "missing".
- Use `null` when you want to *explicitly* say "this is intentionally empty" or when libraries / APIs expect `null`.

Personally, I use `undefined` almost everywhere I’d use `None` in Python or `nil` in Go, and only reach for `null` when the distinction matters or external code requires it.

