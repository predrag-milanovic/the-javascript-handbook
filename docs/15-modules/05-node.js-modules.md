# Node.js Modules

By default, Node.js uses [CommonJS](https://nodejs.org/api/modules.html) for modules. That means files are treated as CommonJS modules unless you explicitly opt into ES module syntax.

There are two ways to switch a Node.js project to ES6 modules:

- Add `"type": "module"` to your `package.json` file.
- Rename your module files from `.js` to `.mjs`.

The first option is usually cleaner and easier to manage, especially in larger projects. If the whole package is meant to use ES modules, `"type": "module"` keeps the file extensions simple and makes the intent obvious.

One important detail: if you're not using ES6 modules, your code will not be in strict mode by default. ES modules are always strict mode, but CommonJS modules are not.
