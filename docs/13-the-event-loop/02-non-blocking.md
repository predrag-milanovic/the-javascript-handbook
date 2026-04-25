# Non-Blocking

So how does JavaScript manage to be efficient with asynchronous code? The answer is the [event loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Execution_model).

The event loop is a single-threaded, non-blocking, event-driven, asynchronous execution model.

We already covered the single-threaded part. Now let's focus on what [non-blocking](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Execution_model#never_blocking) means.

## A Blocking Example

In Python, `time.sleep()` blocks execution while the program waits:

```python
import time

print("Start")
time.sleep(2)
print("Middle")
time.sleep(2)
print("End")
```

That program prints `Start`, waits 2 seconds, prints `Middle`, waits another 2 seconds, and finally prints `End`.

The important part is that `time.sleep(2)` is blocking: the program cannot do anything else while it waits.

## The JavaScript Version

JavaScript behaves differently:

```javascript
console.log("Start");

setTimeout(() => {
	console.log("End");
}, 4000);

console.log("Middle");
```

This prints `Start`, then `Middle` immediately, and then `End` four seconds later.

The main thread in JavaScript cannot be blocked in the same way. That is why `setTimeout()` takes a callback function: it tells the runtime to run that function later, without stopping the rest of the program.

## The Key Idea

The main thread should stay available to do work.

When JavaScript needs to wait, it delegates that waiting to the runtime and schedules the callback for later. That is what makes the language non-blocking.
