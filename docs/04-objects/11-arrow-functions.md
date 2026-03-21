# Arrow functions

[Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) (often called "fat arrow" functions) are a more concise way to write functions in JavaScript. They are newer than the classic `function` keyword and very popular in modern code, but they are **not** always a strict improvement – they just behave a bit differently.

## Three ways to write the same function

You can define the same `add` function in several ways:

```js
// function declaration (not stored in a variable)
function add(x, y) {
	return x + y;
}

// function expression stored in a variable
const add = function (x, y) {
	return x + y;
};

// arrow function expression
const add = (x, y) => {
	return x + y;
};
```

All three versions can be called as `add(2, 3)` and will return `5`.

Arrow functions also support a very compact form when the body is a single expression:

```js
const add = (x, y) => x + y;
```

This version implicitly returns the result of `x + y`.

## What’s different about arrow functions?

Even though the examples above all *look* similar from the outside, arrow functions have some important [differences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions#description) compared to regular functions.

- **Usually used as expressions** – Arrow functions are almost always written as **function expressions** and assigned to a `const` or `let` variable, while `function` can be used for both declarations and expressions.
- **No own `this`** – Arrow functions don’t have their own [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions#no_separate_this), they capture it from the surrounding scope. This often makes object and callback code feel more intuitive, but also means you should not use arrow functions for methods that rely on a dynamic `this`.
- **Not constructors** – Arrow functions cannot be used with `new` and don’t have a `prototype`. You can’t create instances from them: `new Add()` will throw an error if `Add` is an arrow function.
- **No own `arguments`** – Arrow functions don’t have their own `arguments` object. If you need to work with a variable number of parameters, use rest parameters instead: `(...args) => {}`.

In practice, arrow functions are great for small, inline functions (especially callbacks), while regular `function` declarations are still very useful for defining named, reusable functions and constructors.

