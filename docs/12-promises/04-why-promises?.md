# Why Promises?

Promises are one of the cleanest (but not only) ways to handle a common situation: your code needs to request or send data to a server, usually through an [HTTP request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods).

For example, JavaScript's built-in [`fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) returns a promise.

## I/O (Input/Output)

Most promise usage is about I/O.

I/O (input/output) means your code is interacting with something outside the local world of variables and functions.

Common examples of I/O include:

1. HTTP requests
2. Reading files from a hard drive
3. Interacting with a Bluetooth device
4. Sending data to a database

Promises help you handle I/O without freezing your entire program while waiting for responses.
