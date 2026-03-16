# Optional Chaining

Nested data can quickly become hard to work with. In most real-world systems, you’ll often deal with objects that are nested three or four levels deep.

When using the normal `.` operator, if the object on the left side is `null` or `undefined`, JavaScript throws a `TypeError` at runtime.

```js
const tournament = {
	prize: {
		units: "dollars",
		value: 100,
	},
};

const h = tournament.referee.height;
// TypeError: Cannot read properties of undefined (reading 'height')
```

Here, `tournament.referee` is `undefined`, so accessing `.height` crashes.

To avoid this, JavaScript provides the [**optional chaining** operator `?.`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining):

```js
const tournament = {
	prize: {
		units: "dollars",
		value: 100,
	},
};

const h = tournament.referee?.height;
// h is simply undefined, no error is thrown
```

If `tournament.referee` is `null` or `undefined`, the expression stops there and evaluates to `undefined` instead of throwing. If it exists, JavaScript continues and reads `.height` as usual.

## When to chain

You should only use `?.` when you expect that something in the chain may not exist.

For example, if according to your business logic a user must have an `address` object, but the `address` object might not have a `street` property, you would not use optional chaining on `user.address` because you expect it to always be defined:

```js
const street = user.address.street;
```

But if not all users have an address, you might use optional chaining on `address`:

```js
const street = user.address?.street;
```

Or, if you are not even sure if the `user` object itself exists:

```js
const street = user?.address?.street;
```

You do not want to overuse optional chaining. If your system requires that users always have certain objects, and you encounter a user that does not, you probably want an error so you can spot the bug and fix the underlying problem. Good errors make debugging easier.

