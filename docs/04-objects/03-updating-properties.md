# Updating Properties

You can update existing properties and add new ones to an object using dot notation. In this handbook, you’ll see the words *property* and *key* used interchangeably.

If a property already exists, its value is updated. If it does not exist, it is created as a new property:

```js
const apple = {
	name: "Apple",
	radius: 2,
	color: "red",
};

apple.numSeeds = 3;   // new property
apple.color = "green"; // update existing property
```

After these updates, `apple` looks like this:

```js
{
	name: "Apple",
	radius: 2,
	color: "green",
	numSeeds: 3,
}
```

This same pattern works for any object and any property name.

