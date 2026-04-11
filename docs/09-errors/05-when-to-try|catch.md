## When to use `try`/`catch`

Errors are not something to be scared of. Every production program deals with them constantly. Our job is to handle errors gracefully and in a way that matches our expectations for how the code should behave.

One tricky part of JavaScript is knowing whether a function might throw. In some languages (like Go), the function signature makes this explicit:

```go
func getMovieRecord(movieId int) (Movie, error) {
	// ...
}
```

The return type tells you that you should be ready for an error. In JavaScript, we usually do **not** have that signal, so the only way to be sure is to read the function body. That can make you feel like you should just wrap everything in `try`/`catch`, but that usually makes code harder to reason about.

Here are some rules of thumb for when to use `try`/`catch`:

- **Do you control the input?** If a value comes from a user, an API, or any external source, it is more likely to be invalid or unexpected. Wrap the first place you process that input in `try`/`catch`.
- **Is the error recoverable?** If you can reasonably recover (for example, by retrying a network request or showing a fallback UI), then catching the error makes sense. If you cannot recover, it is often better to let the program fail fast instead of hiding the problem.
- **Are you compensating for bad code?** Do not use `try`/`catch` just to cover up sloppy logic that throws a lot. Fix the code instead of masking errors.
- **Is it really “crash-worthy”?** In many JavaScript apps—especially on the front end—there are lots of unknowns. It is not always worth crashing everything just because a value is `undefined`. Modern operators like [optional chaining (`?.`)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining) and [nullish coalescing (`??`)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing) exist to help you handle these cases without throwing. Use them where they make intent clearer than `try`/`catch`.

