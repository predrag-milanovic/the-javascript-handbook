# The Call Stack

JavaScript runs your code on a main thread.

When we talk about asynchronous behavior (`setTimeout`, HTTP requests, and so on), the [event loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Execution_model) is a big part of the story. But before that, we need a quick refresher on the call stack.

Every time a function is called, a new stack frame is pushed onto the call stack. When that function returns, its frame is popped off.

## Example

```javascript
function startJob() {
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

As functions are called, the stack grows:

```txt
[empty] -> startJob -> workOnJob -> finishJob
```

As functions return, the stack shrinks:

```txt
finishJob returns: [startJob, workOnJob]
workOnJob returns: [startJob]
startJob returns: [empty]
```

That is the core behavior: push on call, pop on return.

So far, this is standard call stack behavior you would see in many languages. The interesting part is what happens when asynchronous code is involved, which is what the next lesson covers.
