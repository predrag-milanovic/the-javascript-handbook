# Semi-Colons in JavaScript

In languages like C, C++, and Java, a semicolon is used as a statement terminator. For example, in C:

```c
int x = 5;
```

This allows the compiler to know when a statement ends without relying on whitespace or newlines. For example, this is also valid C:

```c
int x = 5; int y = 10;
```

In JavaScript, semicolons are optional as terminating characters. The JavaScript engine can insert them automatically during the parsing phase (this is called *automatic semicolon insertion*).

However, many developers (us included) prefer to write semicolons explicitly to avoid confusion or subtle bugs that can arise from automatic insertion.

```js
// This works
let x = 5
let y = 10

// But we prefer this
let x = 5;
let y = 10;
```

The most important thing is to pick a style (with or without semicolons) and keep it consistent across your codebase.

