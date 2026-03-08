# Anonymous functions

An **anonymous function** is a function without a name. They are handy when you want to define a function "on the spot"—for example, when you only need it once or when you are creating a quick [closure](https://en.wikipedia.org/wiki/Closure_(computer_programming)).

Suppose we have a `conversions` function that accepts another function, `converter`, as input:

```js
function conversions(converter, x, y, z) {
	const convertedX = converter(x);
	const convertedY = converter(y);
	const convertedZ = converter(z);
	console.log(convertedX, convertedY, convertedZ);
}
```

We could define a function normally and pass it in by name:

```js
// using a named function
function double(a) {
	return a + a;
}

conversions(double, 1, 2, 3);
// 2 4 6
```

But if we only plan to use this function in one place, we can define it inline as an anonymous function:

```js
// using an anonymous function
conversions(
	function (a) {
		return a + a;
	},
	1,
	2,
	3,
);
// 2 4 6
```

Here, the anonymous function is created right where it is needed and passed directly as the `converter` argument. This pattern is very common in JavaScript, especially with callbacks and array methods.

