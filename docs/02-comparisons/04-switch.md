## Switch

[`switch` statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch) let you compare a single value against multiple possible matches. They are similar to chained `if/else if` statements, but can be easier to read when there are many options.

```js
const os = "mac";
let creator;

switch (os) {
	case "linux":
		creator = "Linus Torvalds";
		break;
	case "windows":
		creator = "Bill Gates";
		break;
	case "mac":
		creator = "Steve";
		break;
	default:
		creator = "Unknown";
		break;
}

console.log(creator);
// "Steve"
```

The `switch` statement compares `os` against each `case` using strict equality (`===`). When it finds a matching case, it runs that block.

### Fall-through and `break`

Unlike some languages where `switch` stops automatically after a match, JavaScript will **keep executing the following cases** until it hits a `break`, `return`, or the end of the `switch` block. This behavior is called [*fall-through*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch#breaking_and_fall-through).

```js
const value = 2;

switch (value) {
	case 1:
		console.log("one");
	case 2:
		console.log("two");
	case 3:
		console.log("three");
}

// Logs:
// "two"
// "three"
```

Because there are no `break` statements, once `case 2` matches, execution “falls through” into `case 3` as well.

In day-to-day code, **most** `switch` statements should include a `break` (or `return`) at the end of each case to avoid accidental fall-through. Intentional fall-through can be useful but should be rare and clearly documented.

