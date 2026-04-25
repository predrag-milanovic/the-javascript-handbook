# Microtask Queue

There is one more queue to understand in the event loop: the [microtask queue](https://developer.mozilla.org/en-US/docs/Web/API/HTML_DOM_API/Microtask_guide).

Like the task queue, the microtask queue schedules work to run later. But it follows different rules and is used for shorter-lived operations.

In JavaScript, promise callbacks like `.then()` and `.catch()` are scheduled as microtasks.

## Task Queue vs. Microtask Queue

Two differences matter most:

1. **Execution order**: All queued microtasks run before the event loop picks the next task (sometimes called a macrotask).
2. **Chaining behavior**: A microtask can schedule more microtasks, and those new microtasks also run before the next macrotask.

## Do You Need to Care?

Usually, not much.

Most of the time, it is enough to think: "this asynchronous callback runs later." In day-to-day coding, depending on exact callback ordering is often a code smell.

Still, understanding microtasks helps explain why promises behave differently from APIs like `setTimeout`.

## Example

```javascript
function main() {
	console.log("main start");

	setTimeout(() => {
		console.log("macrotask 1 finished");
	}, 0);

	Promise.resolve()
		.then(() => {
			console.log("microtask 1 finished");
		})
		.then(() => {
			console.log("microtask 2 finished");
		});

	console.log("main end");
}

main();
```

Output:

```txt
main start
main end
microtask 1 finished
microtask 2 finished
macrotask 1 finished
```

The key takeaway: **all pending microtasks run before the next task from the task queue**.
