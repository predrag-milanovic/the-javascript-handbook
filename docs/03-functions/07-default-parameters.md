# Default parameters

In JavaScript, you can give function parameters **default values**. This is especially useful for optional parameters, so your function still behaves sensibly when a caller omits an argument.

Default values are set directly in the function declaration:

```js
function getGreeting(email, name = "there") {
	console.log(
		`Hello ${name}, welcome! You've registered your email: ${email}`,
	);
}

getGreeting("predrag@example.com", "Predrag");
// Hello Predrag, welcome! You've registered your email: predrag@example.com

getGreeting("predrag@example.com");
// Hello there, welcome! You've registered your email: predrag@example.com
```

If the second argument is omitted, the default value `"there"` is used for `name`. Parameters with default values should come **after** all required parameters, so callers can pass arguments in the usual left-to-right order without ambiguity.

