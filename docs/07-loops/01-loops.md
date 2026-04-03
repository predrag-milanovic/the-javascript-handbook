Loops
=====

A traditional `for` loop in JavaScript looks like this:

```js
for (let i = 0; i < 5; i++) {
	console.log(i);
}
// 0
// 1
// 2
// 3
// 4
```

This syntax is common in C-style languages. In English, this code says:

1. Start with `i` equal to `0`. (`let i = 0`)
2. Start a loop iteration if `i` is less than `5`. Otherwise, exit the loop. (`i < 5`)
3. Log `i` to the console. (`console.log(i)`)
4. Add `1` to `i`. (`i++`)
5. Go back to step 2.

The `for` loop syntax has three parts inside the parentheses:

- **Initialization** – run once before the loop starts (`let i = 0`).
- **Condition** – checked before every iteration; if it is `false`, the loop ends (`i < 5`).
- **Final expression** – runs after each iteration, usually to update the loop variable (`i++`).

