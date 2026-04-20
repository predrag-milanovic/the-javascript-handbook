# Await

The [`await`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await) keyword pauses an async function until a promise settles.

If the promise is fulfilled, `await` returns its value.
If the promise is rejected, `await` throws that rejection as an error.

You can think of `await` as a cleaner alternative to chaining `.then()` callbacks in many cases.

### `.then()` Callback

```js
promise.then((message) => {
	console.log(`Resolved with ${message}`);
});
```

### `await` Syntax

```js
const message = await promise;
console.log(`Resolved with ${message}`);
```

In practice, many developers prefer `await` because it often reads more like normal synchronous code.

## Handling Rejections With `try/catch`

When a promise is rejected, `await` throws. That means standard `try/catch` error handling works naturally:

```js
try {
	const message = await promise;
	console.log(`Resolved with ${message}`);
} catch (error) {
	console.log(`Rejected with ${error}`);
}
```

## Important

You can only use `await`:

1. Inside an `async` function, or
2. At top level in JavaScript modules (top-level await).
