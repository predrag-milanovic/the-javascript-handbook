Inheritance
===========

Classes can inherit properties and methods from another class using the [`extends`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/extends) keyword. The class you extend from is often called the *parent* (or *base*) class, and the new one is the *child* (or *derived*) class.

Here's a simple example using Titans:

```js
class Titan {
	constructor(name) {
		this.name = name;
	}
}

class BeastTitan extends Titan {
	speak(msg) {
		console.log(`${this.name} says, "${msg}"`);
	}
}

const beast = new BeastTitan("Zeke");
beast.speak("You know, it's almost like throwing a baseball");
// Zeke says, "You know, it's almost like throwing a baseball"
```

The `BeastTitan` class inherits the `name` property and the constructor behavior from `Titan`, so when you create a `BeastTitan`, it has a `name` just like any `Titan`.

Overriding methods
------------------

A child class can *override* a method it inherits from its parent by defining a method with the same name.

```js
class Titan {
	constructor(name) {
		this.name = name;
	}

	speak() {
		// this gets overridden in the BeastTitan class
		console.log("*titan noises*");
	}
}

class BeastTitan extends Titan {
	speak() {
		console.log(`${this.name} says, "I'm the Beast Titan"`);
	}
}

const pureTitan = new Titan("Eren's mom");
pureTitan.speak();
// *titan noises*

const beast = new BeastTitan("Zeke");
beast.speak();
// Zeke says, "I'm the Beast Titan"
```

In this example:

- `Titan` defines a default `speak()` method.
- `BeastTitan` extends `Titan` and provides its own `speak()` implementation.
- Calling `speak()` on a `Titan` instance uses the parent implementation.
- Calling `speak()` on a `BeastTitan` instance uses the overridden version in the child class.

This is the core of inheritance in JavaScript classes: reuse behavior from a parent class and customize or extend it in child classes.

