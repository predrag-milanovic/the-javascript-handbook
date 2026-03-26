# Objects

How JavaScript uses plain objects to model structured data, attach behavior with methods, and work with `this`, nesting, defaults, and other core language features built on top of objects.

## Lessons in this chapter

- [01 – Objects](./01-objects.md) – creating plain object literals, reading properties with dot and bracket notation, and how objects relate to maps and dictionaries in other languages.
- [02 – No colon when key matches variable name](./02-no-colon.md) – using shorthand property syntax when a property name matches an existing variable.
- [03 – Updating properties](./03-updating-properties.md) – adding new properties, updating existing ones, and seeing how object shape changes over time.
- [04 – Nesting properties](./04-nesting-properties.md) – putting objects inside other objects and accessing deeply nested data.
- [05 – Optional chaining](./05-optional-chaining.md) – safely reading deeply nested properties with `?.` when parts of the path might be missing.
- [06 – Object methods](./06-object-methods.md) – defining functions directly on objects and using `this` to access their properties.
- [07 – Methods can mutate objects](./07-methods-mutate.md) – how methods change the state of the object they belong to, even when the variable is declared with `const`.
- [08 – Initializing missing properties](./08-initializing-props.md) – checking for missing keys and creating properties with sensible default values.
- [09 – Using strings as keys](./09-strings-as-keys.md) – when to use bracket notation, dynamic property names, and keys that come from variables or user input.
- [10 – The `this` keyword](./10-this.md) – how `this` is determined by call-site, and how its value changes across different execution contexts.
- [11 – Arrow functions](./11-arrow-functions.md) – concise function expressions, how arrow functions differ from regular functions, and what that means for `this` and callbacks.
- [12 – Spread syntax](./12-spread-syntax.md) – copying and merging objects with `...`, overwrite rules, and the limitations of shallow copies.
- [13 – Returning objects from functions](./13-return-objects.md) – grouping multiple results into a single returned object instead of juggling positional array values.
- [14 – Object destructuring](./14-destructuring.md) – unpacking properties into local variables and function parameters for clearer, more concise code.
- [15 – Methods are not bound](./15-not-bound.md) – why methods can lose their `this` when passed around, and how to fix it with `.bind`.