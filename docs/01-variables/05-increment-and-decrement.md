## Increment and decrement

In many languages you increment a number using the `+=` operator. JavaScript supports that too, and it also has dedicated operators for changing a value by exactly `1`: `++` (increment) and `--` (decrement).

### Incrementing

[`++`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Increment) adds `1` to the current value of a variable.

```js
let course_rating = 4;

course_rating++;
console.log(course_rating); // 5

course_rating += 5;
console.log(course_rating); // 10
```

- `course_rating++` is a shorthand for `course_rating = course_rating + 1`.
- `course_rating += 5` is a shorthand for `course_rating = course_rating + 5`.

### Decrementing

[`--`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Decrement) subtracts `1` from the current value of a variable.

```js
let course_rating = 11;

course_rating--;
console.log(course_rating); // 10

course_rating -= 5;
console.log(course_rating); // 5
```

- `course_rating--` is a shorthand for `course_rating = course_rating - 1`.
- `course_rating -= 5` is a shorthand for `course_rating = course_rating - 5`.

You’ll often see `++` and `--` used with loops and counters, where changing a number by exactly `1` is very common.

