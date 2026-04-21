# Single-Threaded

JavaScript is famously [**single-threaded**](https://en.wikipedia.org/wiki/Thread_(computing)#Single-threaded_vs_multithreaded_programs).

Even if your machine has many CPU cores, JavaScript code (in one runtime instance) executes on a single main thread. That means only one JavaScript instruction runs at a time.

So yes, JavaScript cannot run two JavaScript computations at the exact same instant on that same thread.

## Does that mean JavaScript is bad at concurrency?

Not at all.

JavaScript is very strong at handling many tasks *concurrently* when those tasks are mostly waiting on external systems, such as:

- Network requests
- File system operations
- Timers
- Database queries

This works because JavaScript is **non-blocking** for I/O-heavy work.

## Mental model

Think of JavaScript like this:

- It executes one instruction at a time on the main thread.
- While waiting for external I/O, the runtime can keep moving and process other callbacks/tasks.
- When the external work completes, JavaScript resumes handling the result.

### Multi-threaded vs single-threaded async

```txt
Multi-threaded program (4 threads running in parallel)

Thread 1  -------------------------------------------------------->
Thread 2  -------------------------------------------------------->
Thread 3  -------------------------------------------------------->
Thread 4  -------------------------------------------------------->


Single-threaded async (JavaScript)

main thread  ----------------------------------------------------->

             |---- HTTP request ---->|
                     |---- database query ---->|
                             |---- file system access ---->|
```

The key idea is that JavaScript itself is still single-threaded, but the system can overlap waiting periods for I/O operations.

## I/O-bound vs CPU-bound work

JavaScript performs very well when work is **I/O-bound** (lots of waiting).

JavaScript struggles when work is **CPU-bound** (heavy computation on the main thread), because long calculations block everything else until they finish.

As a rule of thumb:

- For many concurrent I/O operations, Node.js often performs extremely well.
- For heavy parallel computation, runtimes/languages with strong multi-threaded CPU execution can have an advantage.

This is why understanding the event loop and non-blocking I/O is so important in JavaScript.
