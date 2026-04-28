# Concurrency

## The Single-Threaded Reality

By now you understand that:

- JavaScript has only one thread in the runtime
- The main thread cannot be blocked by asynchronous tasks
- Results from asynchronous tasks are pushed into the task queue

But here's the key question: **How does actual concurrency work?**

Consider this code:

```javascript
setTimeout(() => {
  console.log("Hi I'm async!");
}, 1000);
```

What logic ensures the callback isn't added to the task queue until 1000 milliseconds pass? Or when making an HTTP request, what logic pushes the network response into the task queue when the request completes?

## The Answer: External APIs

The answer is **external APIs**. Functions like [`setTimeout`](https://developer.mozilla.org/en-US/docs/Web/API/Window/setTimeout), [`fetch`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch), and [`addEventListener`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) are not part of the core JavaScript language—they're provided by the host environment (browser, Node.js, Deno, or Bun).

This is the crucial distinction:

- **The JavaScript runtime** (your code + the JS engine) is **single-threaded**
- **External APIs** are **not single-threaded**

The host environment can run these APIs in the background, often on separate threads or using system-level services. When they complete, the host environment pushes their results into the task queue for the event loop to process.

This architecture enables concurrency without breaking JavaScript's single-threaded model—it's a elegant delegation of work to the runtime's host.
