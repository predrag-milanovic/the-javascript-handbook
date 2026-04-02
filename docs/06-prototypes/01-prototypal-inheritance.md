Prototypal Inheritance
======================

Classes are actually a fairly new addition to JavaScript. Under the hood, they are mostly [syntactic sugar](https://developer.mozilla.org/en-US/docs/Glossary/Syntactic_sugar) over the older, more fundamental inheritance system: **prototypes**.

Every object in JavaScript has an internal link to another object called its [**prototype**](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes) (or `[[Prototype]]`). When an object ["inherits"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Inheritance_and_the_prototype_chain) from another, it means that parent object is used as its prototype.

When you access a property on an object, JavaScript will:

1. Look for the property directly on the object.
2. If it doesn't find it, look on the object's prototype.
3. Keep walking up the prototype chain until it finds the property or reaches the end.

One way to create an object with a specific prototype is [Object.create](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create).

```js
const pureTitan = {
	// parent object / prototype
	name: "Eren's mom",
	speak(msg) {
		console.log("*titan noises*");
	},
};

pureTitan.speak();
// *titan noises*

const beastTitan = Object.create(pureTitan); // child object

console.log(beastTitan.name); // reads .name from pureTitan
// Eren's mom

beastTitan.name = "Zeke";
beastTitan.speak = function () {
	console.log(`${this.name} says, "I'm the Beast Titan"`);
};

beastTitan.speak();
// Zeke says, "I'm the Beast Titan"
```

In this example:

- `pureTitan` is a plain object with a `name` and `speak` method.
- `beastTitan` is created with `Object.create(pureTitan)`, so `pureTitan` becomes its prototype.
- Before we override anything, reading `beastTitan.name` or calling `beastTitan.speak()` would fall back to the properties on `pureTitan`.
- After we assign a new `name` and `speak` on `beastTitan`, those **shadow** the properties on the prototype and are used instead.

This prototype chain behavior is the real inheritance model in JavaScript. The `class` and `extends` syntax you used in the classes chapter are built on top of these same prototype links.

