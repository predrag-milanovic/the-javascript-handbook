## Dynamic and weak typing

Like Python, Ruby, and PHP, JavaScript is a **dynamically typed** language. Variable types are only known at runtime, not at compile time. (Yes, tools like TypeScript add static types on top, but that’s a separate layer.)

On top of that, JavaScript is also [**weakly typed**](https://en.wikipedia.org/wiki/Type_safety#Strong_and_weak_typing), which means it will automatically convert values from one type to another in certain operations. This is called *type coercion*, and it can lead to surprising results if you’re not careful.

### An example of type coercion

```js
let answerToLife = 42;
let answerToTheUniverse = "42";

// JavaScript happily mixes numbers and strings
const answerToEverything = answerToLife + answerToTheUniverse;

console.log(answerToEverything);
// "4242"
```

Because one of the values is a string (`"42"`), JavaScript converts the number `42` to a string and **concatenates** them, instead of doing numeric addition.

Understanding that JavaScript is both dynamic (types decided at runtime) and weak (types can be coerced automatically) will help you reason about bugs involving unexpected types.

