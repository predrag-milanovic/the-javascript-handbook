# Errors

This chapter introduces JavaScript errors: what an error object is, how errors are thrown and caught, and how to decide when to handle them versus letting them crash your program.

Use these sections as a guided tour or as quick reference when you need to recall a specific part of error handling:

- [01 - The Error Object](docs/09-errors/01-error-object.md) – What the built‑in `Error` type is, why it exists, and how to work with its `message` property.
- [02 - Handling Errors](docs/09-errors/02-handling-errors.md) – How JavaScript throws errors, what happens with uncaught errors, and how to catch them with `try`/`catch` so your program can keep running.
- [03 - Finally](docs/09-errors/03-finally.md) – The `finally` block and how to run cleanup or finishing logic whether or not an error was thrown.
- [04 - Throwing Errors](docs/09-errors/04-throwing-errors.md) – Throwing your own errors with `throw`, why you should prefer real error objects over throwing strings, and how that helps tooling and debugging.
- [05 - When to try/catch](docs/09-errors/05-when-to-try|catch.md) – Practical rules of thumb for deciding when to wrap code in `try`/`catch`, when to recover, and when to let failures surface.
