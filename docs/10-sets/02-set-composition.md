# Set Composition

JavaScript sets are great for checking if a value exists and for removing duplicates, but they can do more than that. Modern JavaScript runtimes add **set composition methods** that let you combine sets in ways that mirror classic set theory.

These methods all return **new** sets — they do not modify the original ones.

---

## Intersection with `intersection()`

The [`.intersection()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/intersection) method returns a new set containing only the elements that appear in **both** sets.

```js
const heroes = new Set(["eren", "mikasa", "armin", "reiner"])
const villains = new Set(["eren", "reiner", "bertholdt", "annie"])

const samesies = heroes.intersection(villains)

console.log(samesies)
// Set { 'eren', 'reiner' }
```

Here, `samesies` is a new set with the values shared by `heroes` and `villains`.

---

## Difference with `difference()`

The [`.difference()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/difference) method returns a new set containing the elements that are in the **first** set but **not** in the second set.

```js
const heroes = new Set(["eren", "mikasa", "armin", "reiner"])
const villains = new Set(["eren", "reiner", "bertholdt", "annie"])

const nonVillains = heroes.difference(villains)

console.log(nonVillains)
// Set { 'mikasa', 'armin' }
```

`nonVillains` includes only the heroes who are not also in the `villains` set.

---

## Union with `union()`

The [`.union()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/union) method returns a new set containing **all** elements that appear in **either** set (or in both). Because sets automatically remove duplicates, each value appears at most once.

```js
const heroes = new Set(["eren", "mikasa", "armin", "reiner"])
const villains = new Set(["eren", "reiner", "bertholdt", "annie"])

const everyone = heroes.union(villains)

console.log(everyone)
// Set { 'eren', 'mikasa', 'armin', 'reiner', 'bertholdt', 'annie' }
```

---

There are some more [`set methods`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/union), but those are the big three.
