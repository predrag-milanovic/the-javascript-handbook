# CommonJS

So we've started with the less preferred way of doing modules in JavaScript: [CommonJS](https://en.wikipedia.org/wiki/CommonJS). CommonJS is a module system that was created for Node.js before the new [ES6 module syntax](https://nodejs.org/api/esm.html#modules-ecmascript-modules) was introduced. It's still used in Node.js today, but ever since Node added support for ES6 modules, it's become less common. (heh, get it?)

CommonJS is Node.js specific, you can't use it in the browser without some kind of bundler, which we'll talk about in a bit. The defining features of CommonJS are:

- The [`module.exports`](https://nodejs.org/api/modules.html#modules_module_exports) object, which is used to export stuff
- The [`require`](https://nodejs.org/api/modules.html#modules_require) function, which is used to import stuff

## Exporting

```javascript
// math.js
const add = (a, b) => a + b;
const subtract = (a, b) => a - b;

module.exports = {
  add,
  subtract,
};
```
