# Promises

A [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) in JavaScript is similar to a promise you make to a friend: it is a commitment about something that will happen in the future.

For example, imagine I promise to explain promises to you. That promise has two possible outcomes:

1. It is fulfilled, meaning I eventually explained.
2. It is rejected, meaning I failed to explain.

The [Promise object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) represents that eventual fulfillment or rejection. While waiting, the rest of your code can keep running. This is one reason promises are the most common modern way to manage asynchronous code in JavaScript.

## Creating a Promise

The example below creates a promise that waits 1 second, then randomly resolves with "resolved!" or rejects with "rejected!":

```js
const promise = new Promise((resolve, reject) => {
	setTimeout(() => {
		if (getRandomBool()) {
			resolve("resolved!");
		} else {
			reject("rejected!");
		}
	}, 1000);
});

function getRandomBool() {
	return Math.random() < 0.5;
}
```

In `new Promise((resolve, reject) => { ... })`, `resolve` and `reject` are functions provided by JavaScript:

1. Call `resolve(value)` when the async task succeeds.
2. Call `reject(error)` when the async task fails.

## Working With Promises

After creating a promise, you usually handle outcomes with `.then()` and `.catch()`:

1. [`.then()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) runs if the promise is fulfilled.
2. [`.catch()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch) runs if the promise is rejected.

```js
promise
	.then((message) => {
		console.log(`The promise finally ${message}`);
	})
	.catch((message) => {
		console.log(`The promise finally ${message}`);
	});

// If the promise resolves:
// The promise finally resolved!

// If the promise rejects:
// The promise finally rejected!
```
