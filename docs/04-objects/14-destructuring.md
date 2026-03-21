# Object destructuring

When you have an object, it can get repetitive to access each property with the `.` operator over and over. [**Destructuring assignment**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring#object_destructuring) lets you "unpack" properties into local variables in a concise way.

## Basic object destructuring

Instead of writing:

```js
const apple = {
	radius: 2,
	color: "red",
};

const radius = apple.radius;
const color = apple.color;
```

you can use object destructuring:

```js
const apple = {
	radius: 2,
	color: "red",
};

const { radius, color } = apple;
```

Now `radius` and `color` are variables containing the corresponding property values from `apple`.

## Destructuring function return values

Destructuring is especially handy for unpacking values returned from a function:

```js
function getApple() {
	const apple = {
		radius: 2,
		color: "red",
	};

	return apple;
}

const { radius, color } = getApple();

console.log(radius);
// 2
console.log(color);
// red
```

The function returns a single object, and destructuring lets you immediately grab the pieces you care about.

## Destructuring in function parameters

Destructuring also works **directly in function parameters**. This is useful when your function receives an object and you only need some of its properties.

Instead of:

```js
function eatApple(apple) {
	console.log(`ate a ${apple.color} apple with a radius of ${apple.radius}`);
}
```

you can destructure the properties in the parameter list:

```js
function eatApple({ radius, color }) {
	console.log(`ate a ${color} apple with a radius of ${radius}`);
}
```

This makes it clear which properties the function expects and avoids repeating the object name each time.

