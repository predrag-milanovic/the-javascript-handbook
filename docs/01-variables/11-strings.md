# Strings

In JavaScript, a (non-template) string can be written with either single or double quotes:

```js
'Hello'
"Hello"
```

Most projects pick one style (for example, always using double quotes) to keep the codebase consistent and easier to read.

## Indexing

Square brackets are used to access individual characters inside a string.
Characters are indexed from `0` up to `length - 1`, similar to strings and lists in many other languages.

```js
const greeting = "Hello";

greeting[0]; // 'H'
greeting[1]; // 'e'
greeting[2]; // 'l'
greeting[3]; // 'l'
greeting[4]; // 'o'

// you can also get the last character at length - 1
greeting[greeting.length - 1]; // 'o'
```

The [`length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length) property gives you the number of characters in a string, which is especially useful when working with indexes.

