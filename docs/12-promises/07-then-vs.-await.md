# `.then()` vs `await`

In the early days of JavaScript in browsers, promises and `await` did not exist. Asynchronous code was handled with callbacks.

A callback is a function you pass to another function so it can run later. The [setTimeout](https://developer.mozilla.org/en-US/docs/Web/API/Window/setTimeout) function we've used in the past is a good example.

```js
function callbackFunction() {
	console.log("calling back now!");
}

const milliseconds = 1000;
setTimeout(callbackFunction, milliseconds);
```

Promises improved this model with `.then()`, and later `async`/`await` made many promise flows even easier to read.

## Chained `.then()`

```js
fetchRecipient()
	.then((recipient) => {
		return fetchMessageForRecipient(recipient.id);
	})
	.then((message) => {
		return fetchDeliveryStatus(message.id);
	})
	.then((status) => {
		console.log(`The status is ${status}`);
	});
```

## Equivalent `await`

```js
const recipient = await fetchRecipient();
const message = await fetchMessageForRecipient(recipient.id);
const status = await fetchDeliveryStatus(message.id);
console.log(`The status is ${status}`);
```

As a general rule, prefer `async` and `await` over nested callbacks and long `.then()` chains when possible.

## Why You Still See `.then()`

The `.then()` API was introduced before `async` and `await`, so many older codebases still use it heavily.

Both approaches are valid, and you should be comfortable reading both styles.
