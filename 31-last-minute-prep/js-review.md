# JavaScript / TypeScript Quick Reference

## Core Concepts
*   **Event Loop:** Call Stack -> Web APIs -> Callback Queue -> Event Loop. (Microtasks like Promises execute before Macrotasks like setTimeout).
*   **Closures:** A function bundled with its lexical environment. Allows inner functions to access outer scope variables even after outer function has returned.
*   **`this` Keyword:** Value depends on how the function is called. (Arrow functions do not bind their own `this`, they inherit from parent scope).
*   **Prototypal Inheritance:** Objects link to other objects via `__proto__`. `Object.create(proto)`.
*   **Hoisting:** `var` and `function` declarations are moved to the top of their scope. `let` and `const` are hoisted but uninitialized (Temporal Dead Zone).

## Array Methods (O(N) unless noted)
*   `map()`: Returns new array, transforms elements.
*   `filter()`: Returns new array, filters by condition.
*   `reduce()`: Accumulates values to a single output.
*   `forEach()`: Iterates, returns undefined.
*   `sort()`: Mutates original array. Converts to strings by default (use `(a, b) => a - b` for numbers). Time complexity depends on engine (usually O(N log N)).
*   `splice()`: Mutates. Adds/removes elements anywhere.
*   `slice()`: Returns shallow copy of a portion of an array.

## Object & Map
*   **Object:** String/Symbol keys. Unordered. `Object.keys()`, `Object.values()`, `Object.entries()`.
*   **Map:** Any type for keys. Maintains insertion order. `.set()`, `.get()`, `.has()`, `.size`. Better for frequent additions/removals.
*   **Set:** Collection of unique values. `.add()`, `.has()`. Good for deduplication.

## Promises & Async/Await
```javascript
// Promise.all (Fails fast if one rejects)
Promise.all([p1, p2]).then(results => ...);

// Promise.allSettled (Waits for all, returns array of objects with status)
Promise.allSettled([p1, p2]).then(results => ...);

// Async/Await syntax
async function fetchUser() {
  try {
    const res = await api.getUser();
    return res.data;
  } catch (error) {
    console.error(error);
  }
}
```
