# Map Keys

In JavaScript, map keys can be any value. That includes strings, numbers, objects, arrays, and even functions.

That flexibility sounds nice, but there’s an important catch: objects and arrays are compared by reference, not by value.

```js
const map = new Map();

map.set(["hello", "there"], "general kenobi");

console.log(map.get(["hello", "there"])); // undefined
```

Even though those arrays contain the same values, they are different array objects in memory. Because they are not the same reference, `Map` treats them as different keys.

If you reuse the exact same array or object reference, it works:

```js
const map = new Map();
const greetingKey = ["hello", "there"];

map.set(greetingKey, "general kenobi");

console.log(map.get(greetingKey)); // "general kenobi"
```

This is valid JavaScript, but it is usually not a good idea for everyday code. In most cases, you should use strings or numbers as map keys. They are easier to read, easier to compare, and less likely to surprise you later.
