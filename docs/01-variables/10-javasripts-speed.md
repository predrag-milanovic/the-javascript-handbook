# JavaScript's speed

Comparing the "speed" or efficiency of programming languages is not an exact science.
There are many variables and moving parts, so benchmarks can be misleading.
Still, it is useful to have some high-level intuition about where JavaScript fits.

## Compared to low-level languages

- JavaScript is generally not as fast as languages like C, Rust, or Zig.
- These languages usually do not use garbage collection and can be optimized very aggressively.

## JIT compilation

Modern JavaScript engines (like [V8](https://v8.dev/)) typically **JIT-compile** (just-in-time compile) JavaScript into machine code at runtime.

- This is usually slower than **AOT** (ahead-of-time) compilation used by languages like Go or Java.
- It is usually much faster than purely interpreted languages like Python or Ruby.

## Single-threaded, asynchronous

JavaScript runs on a single main thread, but has excellent support for asynchronous programming.

- It is typically not ideal for CPU-bound work (for example, heavy numerical calculations).
- It performs well for I/O-bound work (for example, talking to databases or making API calls).

