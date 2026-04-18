# Why Async?

Whenever possible, we prefer synchronous code because it is easier to reason about and usually less error-prone.

However, some work naturally takes time, especially network operations. If a user updates settings on a website, the browser must send an HTTP request to a server and wait for a response. That wait can be short or long depending on network conditions.

## Synchronous

In a synchronous flow, Process A waits until Process B finishes and responds.

```text
+-----------+                 +-----------+
| Process A |                 | Process B |
+-----------+                 +-----------+
	|                             |
	| -------- request ---------> |
	|                             |  (waiting to start)
	|                             v
	|                      [processing]
	|                             |
	| <-------- response -------- |
	|                             |
 (waiting for response)             |
	v                             v
    [done]                       [done]
```

## Asynchronous

In an asynchronous flow, Process A sends the request and continues doing other work while Process B processes it.

```text
+-----------+                 +-----------+
| Process A |                 | Process B |
+-----------+                 +-----------+
      |                             |
      | -------- request ---------> |
      |                             |  (waiting to start)
      |                             v
      |                      [processing]
      |                             |
      | <-------- response -------- |
      |                             |
 (continues working)                |
      |                             v
      v                           [done]
 [still working]
```

If every network request were synchronous, the page would freeze while waiting. Asynchronous code keeps the app responsive by allowing other tasks to run until the response arrives.
