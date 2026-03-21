# Spread syntax

JavaScript has a handy [**spread syntax**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax#spread_in_object_literals) (`...`) for copying and combining groups of object properties. It’s very common when working with configuration objects, state updates, and defaults.

## Copying and merging objects

You can use spread to make a shallow copy of an object and to merge multiple objects into a new one:

```js
const engineeringDept = {
	lane: "grand magus",
	hunter: "software engineer",
	allan: "software engineer",
	matt: "software engineer",
	dan: "software engineer",
	waseem: "software engineer",
};

const videoDept = {
	stass: "video producer",
	alex: "video producer",
};

const allEmployees = { ...engineeringDept, ...videoDept };
/*
{
	lane: "grand magus",
	hunter: "software engineer",
	allan: "software engineer",
	matt: "software engineer",
	dan: "software engineer",
	waseem: "software engineer",
	stass: "video producer",
	alex: "video producer",
}
*/
```

Here `allEmployees` is a new object that contains the properties from both `engineeringDept` and `videoDept`.

## Property overwrite rules

When you spread multiple objects into a new one, **properties with the same name are overwritten by later spreads**. The right-most spread wins:

```js
const engineeringDept = {
	lane: "software engineer",
	hunter: "software engineer",
};

const videoDept = {
	lane: "cringe youtuber",
	alex: "video producer",
};

const allEmployees = { ...engineeringDept, ...videoDept };
/*
{
	lane: "cringe youtuber",
	hunter: "software engineer",
	alex: "video producer",
}
*/
```

In this example, both objects define `lane`, but the value from `videoDept` overwrites the value from `engineeringDept` because `videoDept` appears later in the spread.

## Shallow copy only

Object spread creates a [**shallow copy**](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy): it copies property references, not deep clones. If a property value is another object or array, both the original and the copy will still point to the same nested value.

