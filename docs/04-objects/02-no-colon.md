## No colon when key matches variable name

The `key: value` syntax is the normal way to create key–value pairs in an object. However, if you want a key to have the **same name** as an existing variable, you can omit both the colon and the value.

These two snippets are equivalent:

```js
const radius = 2;
const color = "red";

const apple = {
	radius: radius,
	color: color,
};
```

Using the shorthand syntax:

```js
const radius = 2;
const color = "red";

const apple = {
	radius, // same as radius: radius
	color,  // same as color: color
};
```

When the property name and variable name match, the shorthand form is usually preferred because it is less verbose and easier to read.

