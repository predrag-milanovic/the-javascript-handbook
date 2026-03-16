# Nesting Properties

Objects can contain other objects as values. In this case, we say that the properties are *nested*.

Here we nest two object literals, `referee` and `prize`, inside the `tournament` object:

```js
const tournament = {
	referee: {
		name: "Sally",
		age: 25,
	},
	prize: {
		units: "dollars",
		value: 100,
	},
};
```

You access nested properties by chaining property names with dot notation:

```js
console.log(tournament.referee.name);  // "Sally"
console.log(tournament.prize.value);   // 100
```

Each `.` steps one level deeper into the object:

- `tournament` → the outer object
- `tournament.referee` → the nested `referee` object
- `tournament.referee.name` → the `name` property inside `referee`

This same pattern works for any depth of nesting.

