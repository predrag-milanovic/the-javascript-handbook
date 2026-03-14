# Objects

JavaScript [objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) are a versatile way to group related data and behavior using key-value pairs. Plain object literals (often called POJOs, for "plain old JavaScript objects") are the most common way to create them.

```js
const apple = {
	name: "Apple",
	radius: 2,
	color: "red",
};
```

Each entry inside the curly braces is a property: a name (the key) followed by a value.

You can access properties stored on an object using the dot (`.`) operator:

```js
console.log(apple.name); // "Apple"
console.log(apple.radius); // 2
console.log(apple.color); // "red"
```

You’ll also sometimes see bracket notation, which treats the property name like a string key:

```js
console.log(apple["name"]);
```

In many other languages you might use a map or dictionary for simple key-value data. In JavaScript, plain objects fill that role, but they’re also used for more advanced features like prototypes and classes—which you’ll see later in this handbook.

