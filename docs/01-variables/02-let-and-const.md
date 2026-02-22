# let and const

In modern JavaScript, you should declare variables with **let** and **const**, not `var`.

The "old" way to declare variables is with `var`:

```js
var mySkillIssues = 42
```

This still works, but you should avoid it in new code.

Instead, use `let`:

```js
let mySkillIssues = 42
```

Or `const` (short for **constant**) for values that you do **not** plan to change:

```js
const mySkillIssues = 42
```

If you try to reassign a `const` variable, you’ll get an error:

```js
const mySkillIssues = 42
mySkillIssues = 43 // TypeError: Assignment to constant variable.
```

Whereas with `let`, you can reassign the value without any issue:

```js
let mySkillIssues = 42
mySkillIssues = 43 // No error
```

**Rule of thumb:**

- Use `const` by default, for values you don’t intend to reassign.
- Switch to `let` only when you know you’ll need to reassign the variable.

---

## Why avoid var?

The big problem with `var` is that it’s **function-scoped**, not **block-scoped**, which often leads to surprising behavior.

Most developers expect block scope. For example:

```js
if (true) {
	var mySkillIssues = 42
}

console.log(mySkillIssues) // 42
```

Here, `mySkillIssues` is **not** limited to the `if` block. It “escapes” and is available outside the block.

With `let` and `const`, variables are **block-scoped**:

```js
if (true) {
	let mySkillIssues = 42
	const myConstSkillIssues = 43
}

console.log(mySkillIssues) // ReferenceError: mySkillIssues is not defined
console.log(myConstSkillIssues) // ReferenceError: myConstSkillIssues is not defined
```

Both `mySkillIssues` and `myConstSkillIssues` exist only inside the `if` block. This behavior is usually what you want and makes code easier to reason about.

In summary:

- Prefer `const` and `let` in all modern JavaScript.
- Treat `var` as legacy syntax that you’ll only see in older codebases.

