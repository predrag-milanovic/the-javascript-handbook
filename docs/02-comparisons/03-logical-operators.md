# Logical operators

If you’re coming from Python, you might be used to the logical operators being written as words:

- `and`
- `or`
- `not`

In JavaScript, the same ideas exist but they are written with symbols instead of words.

## JavaScript logical operators

- `&&` (**and**) – returns `true` only if **both** conditions are true.
- `||` (**or**) – returns `true` if **at least one** of the conditions is true.
- `!` (**not**) – flips a boolean: `true` becomes `false`, `false` becomes `true`.

```js
true && true;  // true
true && false; // false

true || false; // true
false || false; // false

!false; // true
!true;  // false
```

This symbolic syntax matches many other languages such as Go, Rust, C, and C++, so if you know those already, JavaScript will feel familiar here.

