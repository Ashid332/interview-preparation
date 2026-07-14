# Node.js Interview Guide

## Overview
Node.js is a JavaScript runtime built on Chrome's V8 engine. It uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfectly suited for data-intensive real-time applications that run across distributed devices.

## Interview Questions

### Q1: Explain the Event Loop in Node.js.
**Difficulty:** Medium | **Frequency:** High | **Companies:** Netflix, Uber, PayPal
**Excellent Answer:**
The Event Loop is what allows Node.js to perform non-blocking I/O operations despite being single-threaded. It offloads operations to the system kernel (which can be multi-threaded) whenever possible. The loop consists of several phases: timers, pending callbacks, idle/prepare, poll, check, and close callbacks.
**Common Mistakes:**
- Confusing it perfectly with browser event loops.
- Stating Node.js is completely single-threaded (libuv uses a thread pool under the hood).

## Real-World Applications
- Real-time chat applications (using WebSockets).
- Single Page Application (SPA) servers.
- Streaming applications (video/audio).
- API Gateways and microservices.

## Practice Problems

| Problem | Description | Difficulty |
|---------|-------------|------------|
| Build a Rate Limiter | Implement middleware to limit API requests per IP without blocking the thread. | Medium |
| Stream Processing | Read a massive CSV file, transform it, and write to a new file using Streams. | Hard |
| Custom EventEmitter | Implement your own version of Node's EventEmitter class. | Medium |

## Hiring Manager Perspective
"When interviewing for Node.js roles, I look for a deep understanding of its asynchronous nature. Many developers can write Node code, but few truly understand memory leaks, the event loop phases, and how to debug CPU-intensive blocking operations."

## AI Interview Coach
**Prompt:**
> "Act as a senior engineering manager interviewing me for a backend Node.js position. Ask me three progressively harder questions about Node.js performance optimization, focusing on streams and memory management. Evaluate my answers."
