# Using strings as keys

Dot notation like `desk.height` is great when the property name is **static** – you know the key ahead of time. But sometimes the key is **dynamic**: maybe it comes from user input, a variable, or a function parameter.

In those cases, you use **bracket notation**.

```js
const desk = {
	wood: "maple",
	width: 100,
};

console.log(desk.wood);
// prints "maple"

console.log(desk["wood"]);
// also prints "maple"

const key = "wood";
console.log(desk[key]);
// also prints "maple"
```

With bracket notation, the expression inside the brackets is evaluated at runtime, and its string value is used as the property name.

That’s especially useful when the key is passed in as an argument:

```js
function getLastName(users, firstName) {
	return users[firstName];
}
```

Here `firstName` is a string, and `users[firstName]` looks up the matching property on the `users` object. Dot notation can’t do this, because `users.firstName` would always look for a property literally named `"firstName"`.

