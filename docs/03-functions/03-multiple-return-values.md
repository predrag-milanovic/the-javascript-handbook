# Multiple Return Values

Many languages allow multiple values to be returned from a function. For example, in Python this works:

```py
def get_user():
		return "name@domain.com", 21, "active"

email, age, status = get_user()
```

However, in JavaScript, that's not allowed in the same way.

```js
function getUser() {
	return "name@domain.com", 21, "active";
	// DON'T DO THIS
	// it only returns 'active'
}
```

Strangely, the JavaScript code above doesn't throw an error. Instead, because of the comma operator, the function silently returns just the last value: the string `"active"`. This is unintuitive behavior that you probably didn't want.

In JavaScript, you can only return a single value from a function. To work around this, most developers return an object that contains all the values they want to return. We'll cover objects later.

