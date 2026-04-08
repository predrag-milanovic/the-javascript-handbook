# `const` Arrays

Just like objects, arrays declared with `const` can still have their **contents** changed. The `const` keyword only prevents you from **reassigning** the variable to a different value.

You can add, remove, or update elements in a `const` array:

```js
const drinks = []

drinks.push("lemonade")
console.log(drinks)
// Prints: ['lemonade']

drinks[0] = "soda"
console.log(drinks)
// Prints: ['soda']
```

But you **cannot** assign a brand new array to the same `const` variable:

```js
const drinks = ["lemonade"]

drinks = ["root beer"]
// TypeError: Assignment to constant variable.
```

In other words:

- The **binding** (the variable name `drinks`) is constant.
- The **value it points to** (the array) is still mutable.

Some developers find this surprising because `const` can sound like “won’t change at all”. In JavaScript, it really means “won’t be reassigned”. If you want an array whose contents truly never change, you need additional techniques (for example, never mutating it, or using helper functions that return new arrays instead of changing the original).

