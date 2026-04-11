## Throwing errors

So far, we have seen errors that the JavaScript runtime throws for us. Sometimes, though, *you* need to throw an error on purpose.

Use the [`throw`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/throw) statement to signal that something went wrong:

```js
throw new Error("Something went wrong");
```

JavaScript technically lets you throw *anything*, not just error objects:

```js
throw "Something went wrong";
```

However, for consistency and maintainability, you should always throw proper error objects (like `Error` or custom error classes). They carry a message, a stack trace, and work better with tooling and logging.

