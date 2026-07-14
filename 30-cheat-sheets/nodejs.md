# Node.js Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| Event Loop | The core mechanism that handles asynchronous I/O in Node's single-threaded environment (libuv). |
| Streams | Concept for handling reading/writing data continuously (Readable, Writable, Duplex, Transform). |
| Buffers | Temporary memory spots for chunks of data being transferred. |
| Child Processes | Used to scale Node applications by running non-blocking background tasks or utilizing multi-core systems. |

## Must-Know Items
- The phases of the Event Loop (Timers, Pending Callbacks, Idle/Prepare, Poll, Check, Close Callbacks).
- Express.js middleware pattern.
- CommonJS (`require`) vs ES Modules (`import`).
- Error handling in async code and preventing unhandled promise rejections.

## Common Interview Questions (Quick)
1. How does Node.js handle concurrency despite being single-threaded?
2. What are streams and why are they useful?
3. Explain `process.nextTick()` vs `setImmediate()`.
4. How do you prevent blocking the event loop?

## Critical Commands/Patterns
```javascript
// Express Middleware Pattern
app.use((req, res, next) => {
  console.log('Time:', Date.now());
  next(); // Pass control to next middleware
});

// Stream processing
const fs = require('fs');
fs.createReadStream('input.txt').pipe(fs.createWriteStream('output.txt'));
```

## Decision Framework
- **CPU vs I/O bound:** Node is excellent for I/O bound tasks (web servers, APIs). Avoid using Node for heavy CPU-bound tasks (video encoding) on the main thread; use Worker Threads instead.
- **Streams vs reading to memory:** If file/data > available memory, always use Streams to process in chunks.

## Common Mistakes
- Writing synchronous code (`readFileSync`) in the main server logic, blocking all other requests.
- Callback Hell (avoid by using Promises/Async-Await).
- Forgetting to handle the `error` event on streams, which crashes the process.

## One-Minute Review
- Node is a runtime for JS outside the browser. Master the asynchronous, non-blocking I/O model, the event loop, Express middleware, and stream handling.
