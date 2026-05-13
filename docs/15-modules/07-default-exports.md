# Default Exports

There is one more export style you will see when working with modules: default exports.

Default exports are usually used when a module exposes one main value.

Example with named exports:

```js
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;

// main.js
import { add, subtract } from "./math.js";
```

This exports two values, and both are imported with curly braces.

If you want one default export, you can write:

```js
// math.js
const add = (a, b) => a + b;
const subtract = (a, b) => a - b;

export default add;
```

Then import it without curly braces:

```js
// main.js
import add from "./math.js";
```

You can also combine default and named exports:

```js
// math.js
export const subtract = (a, b) => a - b; // named export

const add = (a, b) => a + b;
export default add; // default export

// main.js
import add, { subtract } from "./math.js";
```

## Should You Use Default Exports?

You can, but many teams prefer named exports only.

Why teams often prefer named exports:

- Refactors are easier when a module grows from one export to many.
- Import names are explicit and consistent across files.
- Auto-import and code navigation are often clearer.

Practical rule of thumb:

- Use named exports by default.
- Use a default export only when the module truly has one primary value (for example, one UI component per file).
