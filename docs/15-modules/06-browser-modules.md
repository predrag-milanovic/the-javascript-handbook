# Browser Modules

Modern browsers support ES modules (ESM) natively. To make a script behave as a module in the browser, you must add the `type="module"` attribute to the `<script>` tag. Ordinary script tags are not modules and are executed as classic scripts in the global scope.

Example — classic scripts (not modules):

<script src="meFirst.js"></script>
<script src="meSecond.js"></script>

Classic scripts run in order, immediately when encountered during parsing (unless you add `defer` or `async`). They share the global scope, so variables and functions defined there may pollute `window`.

Example — module scripts:

<script type="module" src="math.js"></script>
<script type="module" src="main.js"></script>

Key differences and benefits of module scripts

- Modules are scoped: values declared inside a module are not added to the global scope. To expose values to other modules you must export them with `export` and import them with `import`.
- Modules are deferred by default: module scripts are executed after the document has been parsed (like adding `defer` to a classic script). This avoids blocking HTML parsing and DOM construction.
- Modules use strict mode automatically: you don't need to add `"use strict"` — strict mode is enabled for module code.

Quick notes and best practices

- Importing and exporting:

```js
// math.js
export function add(a, b) { return a + b }

// main.js
import { add } from './math.js'
console.log(add(2, 3))
```

- Execution order: module scripts are deferred and will run after parsing. If you include multiple module scripts without import relationships, they will execute in the order they appear in the document. When modules import one another, the browser resolves dependencies and executes modules in the correct dependency order.

- Dynamic imports: you can load modules on demand with `import()` which returns a Promise.

```js
import('./optional-feature.js').then(mod => {
	mod.doFeature()
})
```

- CORS and `type="module"`: module scripts are subject to stricter origin and MIME-type checks in some browsers. When loading modules from other origins, ensure the server sends the correct CORS headers.
