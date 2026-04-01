# Private Properties

By default, all properties of a class are *public*, meaning they can be read and changed from outside the class.

```js
class Movie {
	constructor(title, rating) {
		this.title = title;
		this.rating = rating;
	}
}

const matrixMovie = new Movie("The Matrix", 9.5);

console.log(matrixMovie.title);
// The Matrix

matrixMovie.title = "The Matrix Reloaded";

console.log(matrixMovie.title);
// The Matrix Reloaded
```

Sometimes you *don’t* want callers to be able to reach in and change things directly. That’s where **private fields** come in.

---

## Defining a Private Field

You can make a property [private](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/Private_elements) by prefixing it with `#` and declaring it at the top of the class.

```js
class Movie {
	#title;

	constructor(title, rating) {
		this.#title = title;
		this.rating = rating;
	}
}

const matrixMovie = new Movie("The Matrix", 9.5);

console.log(matrixMovie.#title);
// Uncaught SyntaxError: Private field '#title' must be declared in an enclosing class
```

Private fields are truly private: you cannot access `#title` from outside the class body.

---

## Using Private Fields Inside the Class

Private fields are still fully usable *inside* the class methods.

```js
class Movie {
	#title;

	constructor(title, rating) {
		this.#title = title;
		this.rating = rating;
	}

	getTitleAllCaps() {
		const allCaps = this.#title.toUpperCase();
		return allCaps;
	}
}

const matrixMovie = new Movie("The Matrix", 9.5);

console.log(matrixMovie.getTitleAllCaps());
// THE MATRIX
```

Here, the class controls how (or if) the title is exposed to the outside world.

---

## Encapsulation

Encapsulation in JavaScript usually happens at two levels:

- **Class level** – using `#` for private fields and keeping some methods internal.
- **Module level** – exporting only what you want to be public (more on modules later).

Private fields help keep your objects’ internal state safe from accidental (or intentional) misuse. If you need to expose something, you can do it through methods or getters instead of raw property access.

