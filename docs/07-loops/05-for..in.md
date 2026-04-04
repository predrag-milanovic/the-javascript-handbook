For...in
========

Sometimes it's useful to loop over all the keys of an object. The `for...in` loop lets you iterate over the **enumerable string keys** of an object, which is handy when you're using an object like a dictionary or hash map.

```js
const titan = {
	name: "Eren",
	power: "Attack Titan",
	age: 19,
};

for (const key in titan) {
	console.log(`${key}: ${titan[key]}`);
}
// name: Eren
// power: Attack Titan
// age: 19
```

In modern JavaScript specifications, the traversal order for `for...in` is well-defined and consistent across implementations:

- For each object in the prototype chain, all non-negative integer keys (those that can be array indices) are visited first, in ascending numeric order.
- Then, the remaining string keys are visited in the order they were created.

Even with this rule, the order isn't always obvious when skimming code. If the exact ordering of keys really matters, it's often clearer to first collect the keys into an array and sort them yourself:

```js
const keys = Object.keys(titan).sort();
for (const key of keys) {
	console.log(`${key}: ${titan[key]}`);
}
```

That way, anyone reading the code can immediately see how the keys will be ordered.

