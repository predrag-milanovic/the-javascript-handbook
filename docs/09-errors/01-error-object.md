# The Error Object

Errors in JavaScript are represented by instances of the built-in [`Error`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error) class (and its subclasses like `TypeError`, `RangeError`, and so on).

It’s a simple object whose job is to describe what went wrong.

## The `message` property

The most important property on an `Error` object is `message`: a human-readable description of the problem.

```js
const err = new Error("We've run out of baked salmon");

console.log(err.message);
// We've run out of baked salmon
```

When you create your own errors, always set a clear `message`. That’s what you (and any logging or monitoring tools) will see when something goes wrong.

