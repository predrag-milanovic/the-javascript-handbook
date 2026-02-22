# Basic Data Types

In JavaScript, everything starts with a few **primitive data types** — simple values that are not objects and have no methods of their own.

## Core Data Types

Here are the most common primitive types in JavaScript:

- [**boolean**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) — a logical type that can be either `true` or `false`
- [**string**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) — text enclosed in quotes
- [**number**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) — includes both whole numbers and decimals
- [**undefined**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) — indicates that a variable has been declared but hasn’t been assigned any value yet

There are a few more specialized types such as `null`, `bigint`, and `symbol`, which we’ll cover later.

---

## Declaring Variables

You can create variables in a few different ways.  
We’ll get into modern syntax soon, but let’s start with the traditional `var` keyword to see the basics in action:

```js
var isHungry = true
var hasPet = false

var city = "Banja Luka"

var temperature = 23
var heightInMeters = 1.82

var favoriteColor = undefined
