# Object methods

JavaScript objects can have **methods**, just like classes in Python or structs in Go.

Objects in JavaScript are interesting because they play the role of both dictionaries *and* classes from other languages (yes, JavaScript also has classes—we will get to them later).

Methods are functions that are defined directly on an object. They can access and change that object’s properties.

Inside an object method, the [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) keyword refers to the object itself (similar to `self` in Python). We will talk about the slightly tricky rules for `this` in more detail later.

```js
const person = {
	firstName: "Predrag",
	lastName: "Milanovic",
	getFullName() {
		return this.firstName + " " + this.lastName;
	},
};

console.log(person.getFullName());
// "Predrag Milanovic"
```

Here, `getFullName` is a method on the `person` object. When we call `person.getFullName()`, `this` inside the method points to `person`, so it can read `firstName` and `lastName` from the same object.

