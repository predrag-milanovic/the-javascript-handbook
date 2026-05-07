# ES6 Modules

ES6 modules are the preferred way to structure JavaScript. They are built into the language and supported in modern browsers and Node.js. Below are concise explanations, examples, and common [gotchas](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) to watch for.

## The syntax

Exporting and importing with ES6 modules uses the [`export`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export) and [`import`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import) keywords. The basic idea is simple: a module declares what it exposes with `export`, and another file brings those exports in with `import`.

### Exporting (named exports)

math.js

```js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
```

### Importing (named imports)

main.js

```js
import { add, subtract } from "./math.js";

console.log(add(1, 2)); // 3
console.log(subtract(1, 2)); // -1
```

### Default exports

You can export a single default value from a module and import it without braces:

defaultExport.js

```js
export default function multiply(a, b) {
	return a * b;
}
```

```js
import multiply from "./defaultExport.js";
console.log(multiply(2, 3)); // 6
```

### Other import forms

- Import everything as an object: `import * as math from "./math.js";`
- Rename on import: `import { add as sum } from "./math.js";`

## Important behavior and gotchas

- Modules are always in strict mode.
- Module imports are live bindings: if an exported value changes in the source module, imports observe the update (for mutable bindings).
- Browser imports usually require the file extension (`./math.js`) and `<script type="module">` when loading modules in HTML.
- In Node.js you must opt into ES modules either by using the `.mjs` extension or by setting `"type": "module"` in `package.json`.
- Top-level `await` is allowed in modules in environments that support it.
- Circular dependencies can run into ordering issues; because imports are live bindings, some values may be `undefined` during initialization. Design modules to avoid strong initialization-time cycles.
