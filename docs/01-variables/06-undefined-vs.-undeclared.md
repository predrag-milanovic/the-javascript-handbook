## Undefined vs. undeclared

The primitive value [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) represents the absence of a value, but it’s not the same thing as an *undeclared* variable.

### Undefined variables

We get an `undefined` variable when we declare a variable name but don’t assign any value to it:

```js
let favoriteSandersonCharacter; // undefined

console.log(typeof favoriteSandersonCharacter); // "undefined"
```

- The variable name exists in the current scope.
- Its value is simply `undefined`.

### Undeclared variables

If we never declare the variable name at all, the variable is *undeclared*. Accessing it throws a `ReferenceError`:

```js
console.log(favoriteRothfussCharacter); // ReferenceError: favoriteRothfussCharacter is not defined
```

The error message says "not defined", but what it really means is that the variable is undeclared: the name does not exist in the current scope.

### A note about `const` and `undefined`

You can technically create a `const` that is explicitly set to `undefined`, but you must assign it at declaration time:

```js
const favoriteSandersonCharacter; // SyntaxError: missing = in const declaration

const favoriteSandersonCharacter = undefined; // valid, value is undefined
```

Because `const` variables cannot be reassigned, declaring a `const` whose value is `undefined` is rarely useful in practice.

