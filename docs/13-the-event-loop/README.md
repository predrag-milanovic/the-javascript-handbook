# The Event Loop

Understanding the event loop is fundamental to writing effective asynchronous JavaScript. While JavaScript executes code on a single thread, the event loop enables non-blocking, concurrent execution of I/O-heavy operations.

This chapter breaks down the mechanics of how JavaScript achieves concurrency, from the call stack to task queues, and explains the architecture that makes async code possible.

## Lessons

1. **[01 - Single-Threaded](01-single-threaded.md)** — Learn that JavaScript runs on a single main thread, and explore why this doesn't limit concurrency for I/O-bound tasks.

2. **[02 - Non-Blocking](02-non-blocking.md)** — Understand what non-blocking execution means and how JavaScript differs from blocking languages like Python.

3. **[03 - The Call Stack](03-the-call-stack.md)** — Review how function calls push and pop stack frames, setting the foundation for understanding the event loop.

4. **[04 - Task Queue](04-task-queue.md)** — Discover how asynchronous callbacks are queued and executed when the main thread becomes free.

5. **[05 - Microtask Queue](05-microtask-queue.md)** — Explore the separate queue used by promises and learn how microtasks execute before macrotasks.

6. **[06 - Concurrency](06-concurrency.md)** — Tie it all together and understand how external APIs enable true concurrency within a single-threaded runtime.
