# JavaScript Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| Closures | A function that remembers the variables in its lexical scope even when executed outside that scope. |
| Event Loop | Mechanism that handles asynchronous callbacks (Call Stack -> Web APIs -> Callback Queue/Microtask Queue). |
| Hoisting | Variables/function declarations are moved to the top of their scope before execution. |
| Prototypal Inheritance | Objects inherit properties and methods from other objects (prototypes). |

## Must-Know Items
- `let` vs `const` vs `var` (block scope vs function scope).
- Arrow functions vs regular functions (`this` binding).
- Promises and `async/await`.
- Array methods: `map`, `filter`, `reduce`, `forEach`.

## Common Interview Questions (Quick)
1. What is a closure? Provide an example.
2. Explain the difference between `==` and `===`.
3. How does the event loop work?
4. What is event delegation?
5. Write a polyfill for `Array.prototype.map`.

## Critical Commands/Patterns
```javascript
// Closure Pattern (Data Privacy)
function createCounter() {
  let count = 0;
  return function() { return ++count; };
}

// Promises / Async-Await
async function fetchData() {
  try {
    const res = await fetch(url);
    return await res.json();
  } catch (error) {
    console.error(error);
  }
}
```

## Decision Framework
- **Array iteration:** Use `map` for transformations, `filter` for conditions, `reduce` for aggregations, `forEach` for side effects.
- **`this` context:** Use arrow functions to inherit `this` from lexical scope; use regular functions if you need dynamic `this` (like DOM event listeners).

## Common Mistakes
- Misunderstanding `this` context in callbacks.
- Mutating state directly instead of returning new objects/arrays (especially relevant for React).
- Using `var` instead of `let`/`const`, leading to hoisting bugs.
- Not handling Promise rejections.

## One-Minute Review
- JS is single-threaded but handles concurrency via the Event Loop. Understand execution context, closures, and `this`. Master modern ES6+ syntax (destructuring, spread/rest, optional chaining).
