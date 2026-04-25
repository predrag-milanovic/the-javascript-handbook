# Task Queue

We understand the call stack: call a function, it is pushed onto the stack; when it returns, it is popped off.

But what about asynchronous code?

Enter the task queue.

The task queue (also called the message queue) stores asynchronous callbacks that are ready to run. Conceptually, it is just a FIFO queue of work waiting for JavaScript to execute.

JavaScript is single-threaded at the language level, so queued tasks cannot interrupt currently running synchronous code.

## The Rule

The rule is simple:

1. Run the current call stack.
2. When the call stack becomes empty, the event loop asks for the next queued task.
3. If one exists, it is pushed onto the call stack and executed.

That is why asynchronous callbacks run later, even when a timer is set to `0`.

## Example

```javascript
function startJob() {
	setTimeout(() => {
		console.log("Hi I'm async!");
	}, 0);

	console.log("Job started");
	workOnJob();
}

function workOnJob() {
	console.log("Working on job");
	finishJob();
}

function finishJob() {
	console.log("Job finished");
}

startJob();
```

You might expect this output:

```txt
Hi I'm async!
Job started
Working on job
Job finished
```

Actual output:

```txt
Job started
Working on job
Job finished
Hi I'm async!
```

Why? The `setTimeout` callback is queued as a task. It can only run after all current synchronous calls finish and the call stack is empty.
