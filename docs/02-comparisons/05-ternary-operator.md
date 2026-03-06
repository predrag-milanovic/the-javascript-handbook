## Ternary Operator

Sometimes using a multi-line `if/else` block is overkill. The [**ternary operator**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_operator) lets you express a simple conditional in a single [expression](https://en.wikipedia.org/wiki/Expression_(computer_science)):

```js
const price = isMember ? "2.00 €" : "10.00 €";
```

You can read this in plain English as:

> If `isMember` is true, the expression evaluates to `2.00 €`; otherwise it evaluates to `10.00 €`.

The equivalent `if/else` version looks like this:

```js
let price;

if (isMember) {
	price = "2.00 €";
} else {
	price = "10.00 €";
}
```

Both snippets do the same thing, but the ternary form is shorter and keeps the logic inline where the value is used.

## Why is it called “ternary”?

The word *ternary* comes from a Latin root meaning “three”. The ternary operator is the only JavaScript operator that takes **three operands**:

1. A condition, followed by a question mark `?`
2. The expression to evaluate if the condition is truthy, followed by a colon `:`
3. The expression to evaluate if the condition is falsy

In general form:

```js
condition ? exprIfTrue : exprIfFalse
```

## When to use a ternary

You will still use regular `if/else` statements more often than ternaries. Ternaries shine for **small, single-line conditionals**, especially when you’re choosing between two simple values.

However, overusing them or nesting them can quickly hurt readability. For example:

```js
const vehicleName = isTruck
	? "truck"
	: isCar
		? "car"
		: isScooter
			? "scooter"
			: "vehicle";
```

This works, but it’s much harder to read and understand at a glance. A clearer approach is to use `if/else`:

```js
let vehicleName = "vehicle";

if (isTruck) {
	vehicleName = "truck";
} else if (isCar) {
	vehicleName = "car";
} else if (isScooter) {
	vehicleName = "scooter";
}
```

Or even extract the logic into a function:

```js
function getVehicleName(isTruck, isCar, isScooter) {
	if (isTruck) {
		return "truck";
	}
	if (isCar) {
		return "car";
	}
	if (isScooter) {
		return "scooter";
	}
	return "vehicle";
}
```

The main guideline: use ternaries when they **improve** clarity, not just to make code shorter. Remember, code is written for humans first, not machines.

