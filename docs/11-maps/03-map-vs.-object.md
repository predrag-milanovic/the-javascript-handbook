# Map vs. Object

In JavaScript, both objects and maps can store key/value pairs. Plain objects are usually the default choice because the syntax is shorter and more familiar:

```js
const user = {
	id: 1,
	name: "Ada",
};
```

Maps are worth considering when you need a more dynamic key/value store:

```js
const userRoles = new Map();

userRoles.set("ada", "admin");
userRoles.set("grace", "editor");

console.log(userRoles.get("ada")); // "admin"
```

Maps have a few advantages over objects:

* Ordered: map entries preserve insertion order in a straightforward way.
* [Iterable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#iterating_map_with_for...of): you can loop over a map directly with `for...of`.
* Faster for frequent updates: maps are typically a better fit when you do lots of insertions and deletions.
* No extra properties: maps do not come with built-in properties like `constructor` or `__proto__`.

Objects still have their place. They are simple, concise, and usually the best option when your data is known ahead of time or when you want a lightweight record-like structure.

Maps are also more flexible with keys. Object keys are strings or symbols, while map keys can be any value:

```js
const cache = new Map();
const key = { id: 123 };

cache.set(key, "stored value");

console.log(cache.get(key)); // "stored value"
```

So, for most key/value needs, either will work. Use objects when you want the simplest syntax, and use maps when you want predictable ordering, direct iteration, or a more purpose-built dictionary structure.
