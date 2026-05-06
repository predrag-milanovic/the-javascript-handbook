# Strict Mode

JavaScript is a loosey-goosey language, which makes it easy to write code that *looks* fine but fails in surprising ways.

[Strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode) is a way to opt in to a more restrictive set of rules. It was introduced in ES5, and it helps JavaScript in a few important ways:

- It turns some silent errors into thrown errors.
- It removes some language quirks that make optimization harder for JavaScript engines.
- It blocks some syntax that might be reserved for future versions of ECMAScript.

Long story short: when you can use it, strict mode is a good idea.

## Enabling Strict Mode

To enable strict mode for an entire file, put `"use strict";` at the top:

```javascript
"use strict";

// your code here
```

You can also enable it for a single function:

```javascript
function strictFunction() {
	"use strict";
	// your code here
}
```
