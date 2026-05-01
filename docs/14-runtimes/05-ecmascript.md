# ECMAScript

ECMAScript? I thought we were learning JavaScript!

Yes — you are learning JavaScript. ECMAScript (often abbreviated ES) is the language standard that JavaScript implements. It defines the syntax, semantics, and APIs that runtimes (browsers, Node.js, Deno, etc.) provide so code behaves consistently across environments.

> "[ECMAScript was always an unwanted trade name that sounds like a skin disease.](https://en.wikipedia.org/wiki/ECMAScript#:~:text=Eich%20commented%20that%20%22ECMAScript%20was%20always%20an%20unwanted%20trade%20name%20that%20sounds%20like%20a%20skin%20disease.%22)" — Brendan Eich

Why it matters
- Compatibility: ECMAScript ensures different engines implement the same language features.
- Predictability: The standard guides how new features are designed and adopted.
- Evolution: New ECMAScript versions are released annually by TC39 and shape modern JavaScript.

Because engines implement features at different times, developers often use transpilers (like Babel) or polyfills to run newer syntax on older runtimes.

Notable ECMAScript releases

- ES5 (2009)
	- Introduced strict mode and native JSON support.
	- Example (strict mode):

```js
"use strict";
function sum(a, a) { // Syntax error in strict mode: duplicate parameter name
	return a + a;
}
```

- ES6 / ES2015 (2015)
	- Introduced `let` and `const`, arrow functions, classes, template literals, modules, and more.
	- Example (`let`/`const` and arrow):

```js
const PI = 3.14;
let radius = 2;
const area = (r) => PI * r * r;
console.log(area(radius)); // 12.56
```

- ES8 / ES2017 (2017)
	- Introduced `async` / `await` (built on Promises) for clearer asynchronous code.
	- Example (async/await):

```js
async function fetchJson(url) {
	const res = await fetch(url);
	return res.json();
}

fetchJson('/data.json').then(data => console.log(data));
```

Working with ECMAScript today
- Check feature availability for your target runtimes (MDN, Can I Use, or Node release notes).
- Use transpilation and polyfills when you need newer syntax on older engines.
- Prefer writing modern, readable code and rely on build tools to bridge compatibility gaps.
