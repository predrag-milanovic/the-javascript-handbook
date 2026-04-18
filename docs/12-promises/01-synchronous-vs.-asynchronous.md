# Synchronous vs. Asynchronous

Most JavaScript code is [synchronous](https://developer.mozilla.org/en-US/docs/Glossary/Synchronous), which means it runs in sequence: each line executes in order, one after the next.

## Synchronous Example

```js
console.log("I print first");
console.log("I print second");
console.log("I print third");
```

[Asynchronous](https://developer.mozilla.org/en-US/docs/Glossary/Asynchronous) (or async) code does not block the [main thread](https://developer.mozilla.org/en-US/docs/Glossary/Main_thread) in the same way. The main thread continues running later lines, while async work is scheduled and completed when system resources and the event loop allow.

A common built-in example is [`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/setTimeout).

`setTimeout()` accepts:

1. A function to run later.
2. A delay in milliseconds.

After the delay passes, that function is queued and runs when the main thread is available.

## Asynchronous Example (`setTimeout`)

```js
console.log("I print first");

setTimeout(
  () => console.log("I print third because I'm waiting 100 milliseconds"),
  100,
);

console.log("I print second");

// Output:
// I print first
// I print second
// I print third because I'm waiting 100 milliseconds
```
