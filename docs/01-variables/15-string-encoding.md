## String encoding

In JavaScript, strings are sequences of [UTF-16 *code units*](https://en.wikipedia.org/wiki/UTF-16).

Most common characters are represented by a single 16-bit value (2 bytes). This covers:

- The basic [ASCII](https://www.ascii-code.com/) set (letters, digits, punctuation)
- Many characters from non-English languages
- A large set of symbols

However, some characters need **more than 16 bits** to represent. To handle those, JavaScript uses a *pair* of 16‑bit code units (a *surrogate pair*). Emojis are a common example:

```js
const kermit = "🐸";
```

Even though you see one frog, under the hood that emoji uses **two UTF‑16 [code units](https://developer.mozilla.org/en-US/docs/Glossary/Code_unit)**.

### Why this matters

Most of the time, you can freely use Unicode characters (including emojis) in your strings without worrying about the underlying encoding.

But keep in mind:

- A "character" on screen is not always one code unit.
- Some operations that work in terms of code units (like `string.length` or indexing with `string[0]`) may behave differently than you expect when emojis or other surrogate-pair characters are involved.

For everyday use, this is usually fine. Just remember that some characters take up more than one UTF‑16 code unit inside the string.

