# Promises

This chapter introduces asynchronous JavaScript, then builds up from core promise concepts to modern async and await syntax.

You will learn how async code differs from synchronous code, why promises are useful for I/O-heavy work, and how to choose between `.then()` chains and `await`.

## Lessons

1. [01 - Synchronous vs. Asynchronous](./01-synchronous-vs.-asynchronous.md) explains execution order and shows how delayed work is scheduled with `setTimeout`.
2. [02 - Why Async?](./02-why-async?.md) covers why non-blocking flows are essential for responsive apps.
3. [03 - Promises](./03-promises.md) introduces promise states, creation with `new Promise`, and handling results with `.then()` and `.catch()`.
4. [04 - Why Promises?](./04-why-promises?.md) connects promises to real-world I/O, such as HTTP requests and file access.
5. [05 - Await](./05-await.md) shows how `await` simplifies consuming promises and how to handle rejections with `try/catch`.
6. [06 - Async Keyword](./06-async-keyword.md) explains how `async` functions return promises and compares `async` with manual `new Promise()` usage.
7. [07 - Then vs. Await](./07-then-vs.-await.md) compares callback and `.then()`-style flows with equivalent `await` code and discusses legacy patterns.