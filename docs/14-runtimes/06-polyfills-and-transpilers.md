# Polyfills and Transpilers

Programming languages evolve, and JavaScript is no exception. For web developers the challenge is that you don't always control the runtime — users may run older browsers that lack newer language features. Polyfills and transpilers help bridge that gap.

What is a polyfill?
- A [polyfill](https://en.wikipedia.org/wiki/Polyfill_(programming)) is a small piece of code that adds a missing API or behavior to older environments so newer code can run unchanged. Polyfills typically extend built-ins (like `Array`, `String`, or `Promise`) or add global functions.

Example: a tiny polyfill for `Array.prototype.flat` (simplified):

```js
if (!Array.prototype.flat) {
	Array.prototype.flat = function(depth = 1) {
		return this.reduce((acc, val) => acc.concat(Array.isArray(val) && depth > 1
			? val.flat(depth - 1) : val), []);
	};
}
```

When to use polyfills
- Use feature detection (check whether the API exists) and include polyfills only when needed.
- Common delivery methods: bundle polyfills with your app, or request minimal polyfills from a service like polyfill.io.

What is a transpiler?
- A [transpiler](https://en.wikipedia.org/wiki/Source-to-source_compiler) transforms source code written using newer JavaScript syntax into equivalent code that older environments understand. This lets you use modern syntax (modules, `async/await`, optional chaining, etc.) while supporting legacy browsers.
- Transpilation often combines with polyfills for runtime features (e.g., `Promise`, `Symbol`).

Example: `async/await` source code (developer-facing):

```js
async function fetchJson(url) {
	const res = await fetch(url);
	return res.json();
}
```

When transpiled for older engines, the above might be converted into Promises and generator-based helpers (via tools such as [Babel](https://babeljs.io/) and regenerator), paired with polyfills for global APIs.

Popular tools and workflow
- Babel (`@babel/core`, `@babel/preset-env`) — the most widely used transpiler. Use `preset-env` with a `targets` or `browserslist` config to emit only the transforms you need.
- `core-js` and `regenerator-runtime` — provide polyfills and runtime helpers for features transformed by Babel.
- Browserslist — define target environments (e.g., `> 0.5%, last 2 versions, not dead`) so tooling knows what to transpile/polyfill.

Quick example `.babelrc` snippet:

```json
{"presets": [["@babel/preset-env", {"useBuiltIns": "usage", "corejs": 3}]]}
```

Guidelines
- Prefer feature detection over user-agent sniffing.
- Target a realistic set of browsers with Browserslist to avoid over-transpiling or bundling unnecessary polyfills.
- Use `useBuiltIns: "usage"` (or `entry`) with `@babel/preset-env` + `core-js` to include only the polyfills you actually use.
- For libraries, prefer avoiding global polyfills; instead document required environment features so consumers control compatibility.

Summary
- Polyfills add missing runtime APIs; transpilers rewrite newer syntax into older forms. They often work together to let you write modern, readable code while keeping wide browser compatibility.

