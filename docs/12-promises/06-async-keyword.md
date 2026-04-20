# Async Keyword

The [`async`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) keyword is often the simplest way to create functions that return [promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/Promise).

When a function is marked `async`, JavaScript automatically wraps its return value in a promise.

1. Returning a value resolves the promise with that value.
2. Throwing an error rejects the promise.

You can think of `async` as "wrapping" your function in a promise.

Both examples below return a promise for user data.

### `new Promise()`

```js
function getPromiseForUserData() {
	return new Promise((resolve, reject) => {
		fetchDataFromServer()
			.then((user) => {
				resolve(user);
			})
			.catch((error) => {
				reject(error);
			});
	});
}

const promise = getPromiseForUserData();
```

### `async`

```js
async function getPromiseForUserData() {
	const user = await fetchDataFromServer();
	return user;
}

const promise = getPromiseForUserData();
```

In many real-world cases, the `async` version is shorter and easier to read.

## Important Notes

1. `await` can only be used inside an `async` function, or at top level in a JavaScript module.
2. Calling an `async` function always returns a promise.
3. If an `async` function returns a promise, JavaScript adopts that promise's final result.

```js
async function getUserName() {
	return "Ada";
}

getUserName().then((name) => {
	console.log(name); // Ada
});
```
