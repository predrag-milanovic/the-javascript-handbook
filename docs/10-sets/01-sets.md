# Sets

In JavaScript, a [**set**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) is a collection of unique values. If a value shows up more than once, the set keeps just a single copy. Sets are great when you care about **existence** ("is this value present?") more than about ordering or duplicates.

```js
const set = new Set([1, 2, 3, 4, 5, 5, 5, 5])

console.log(set)
// Set { 1, 2, 3, 4, 5 }
```

All the extra `5`s are removed — the set only stores each value once.

---

## Creating and Updating Sets

You can create an empty set and then add values over time using [`.add()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/add):

```js
const set = new Set()

set.add("bertholdt")
set.add("reiner")
set.add("annie")
set.add("bertholdt")

console.log(set)
// Set { 'bertholdt', 'reiner', 'annie' }
```

Adding the same value again does nothing — `"bertholdt"` still appears only once.

To remove a value, use [`.delete()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/delete):

```js
set.delete("annie")

console.log(set)
// Set { 'bertholdt', 'reiner' }
```

---

## When to Use Sets

Sets are especially useful when you:

- Need to remove duplicate values from a collection.
- Want fast checks like `set.has(value)` to see if something is present.
