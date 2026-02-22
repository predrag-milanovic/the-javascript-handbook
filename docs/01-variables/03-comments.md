# Comments

Comments let you add notes to your code that JavaScript will ignore when it runs. They are great for explaining *why* something is written a certain way, or for temporarily disabling code.

JavaScript has two main styles of comments.

---

## Single-line comments

Use `//` for short, one-line comments:

```js
// This is a single-line comment
const age = 42
```

Everything after `//` on that line is treated as a comment and not executed.

---

## Multi-line comments

Use `/* ... */` for comments that span multiple lines:

```js
/*
	This is a multi-line comment.
	None of these lines will run as code.
*/
const name = "Ada"
```

You can also use multi-line comments to temporarily “turn off” blocks of code while debugging.

---

In practice, keep comments clear and focused on intent. If you find yourself explaining *what* the code does in detail, consider if you can make the code itself clearer instead.

