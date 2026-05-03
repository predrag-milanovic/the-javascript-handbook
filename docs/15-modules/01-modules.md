# Modules

Back in the earliest days of JavaScript - when it was but a wee browser-only language that looked like bastardized Java - JavaScript files were small. A callback here, a dynamic element there, and a sprinkle of (gasp) [jQuery](https://jquery.com/) to make it all work.

But as the web has grown, we're not just shipping a bit of interactivity to static HTML pages anymore. We're building full-fledged applications with crazy amounts of state, logic, and dependencies. In the case of [single page applications](https://en.wikipedia.org/wiki/Single-page_application), sometimes HTML is just a shell that gets filled in with JavaScript at runtime.

Long story short, JS needed modules. In Go, you have packages. In Python, you have modules. Now, JavaScript also has modules - they're just a way to split your code into separate files and import the code you need across a large codebase.

Modules in JavaScript exist at the file level, just like Python. So, if you have a file called `math.js` that looks like this:

```javascript
// math.js
const add = (a, b) => a + b;
const subtract = (a, b) => a - b;

module.exports = {
  add,
  subtract,
};
```

You can import and use those functions in another file like this:

```javascript
// main.js
const { add, subtract } = require("./math.js");

console.log(add(1, 2)); // 3
console.log(subtract(1, 2)); // -1
```

This is [CommonJS](https://en.wikipedia.org/wiki/CommonJS) syntax.
