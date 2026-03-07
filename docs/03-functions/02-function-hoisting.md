# Function Hoisting

In Python, a function must be defined before it's used.

But that's not so in JavaScript! As long as a function is defined somewhere in the file, it can be called even before the definition appears.

```js
console.log(getLabel(3));
// prints 'awful'

function getLabel(numStars) {
	if (numStars > 7) {
		return "great";
	} else if (numStars > 3) {
		return "okay";
	} else {
		return "awful";
	}
}
```

This works because JavaScript ["hoists"](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) the function declaration to the top of its scope before the code is executed. During this hoisting phase, the engine sees the `function getLabel(...)` declaration first, so the function is available to call anywhere in the same scope, even earlier in the file.

