# Initializing missing properties

Sometimes you want to make sure an object has a certain property before you use it. If a property doesn’t exist when you try to access it with the dot (`.`) operator, JavaScript gives you `undefined`.

Because `undefined` is a *falsy* value (it behaves like `false` in a boolean context), you can use the logical NOT operator (`!`) to check whether a property is missing and then initialize it.

```js
const balances = {
	lane: 100,
	breanna: 150,
	john: 200,
};

// if bob doesn't have a balance yet,
// create a new property for him
// and set it to 0
if (!balances.bob) {
	balances.bob = 0;
}
```

In this example, `balances.bob` starts out as `undefined`, so `!balances.bob` is `true` and we create the property with a default value of `0`.

Be aware that this pattern treats **any** falsy value (like `0`, `""`, or `null`) as “missing.” If you specifically want to check whether a property exists or is `undefined`, you can use comparisons like `balances.bob === undefined` or the `in` operator instead.

