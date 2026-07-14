# Go (Golang) Interview Guide

## Overview
Go is a statically typed, compiled programming language designed at Google. It is known for its simplicity, fast compilation times, and excellent built-in support for concurrent programming, making it a top choice for cloud-native applications and microservices.

## Interview Questions

### Q1: How do Goroutines differ from OS threads?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Google, Uber, Twitch
**Excellent Answer:**
Goroutines are lightweight, user-space threads managed by the Go runtime, not the OS. They start with a very small stack (e.g., 2KB) that grows dynamically, whereas OS threads typically start with a large, fixed stack (e.g., 1-2MB). The Go runtime multiplexes thousands of Goroutines onto a small number of OS threads (M:N scheduling), significantly reducing the overhead of context switching.
**Common Mistakes:**
- Confusing Goroutines with parallel execution (they are concurrent; parallel execution depends on `GOMAXPROCS` and CPU cores).

## Real-World Applications
- High-performance web servers and APIs.
- Cloud infrastructure and CLI tools (Docker, Kubernetes).
- Network programming and load balancers.
- Distributed systems.

## Practice Problems

| Problem | Description | Difficulty |
|---------|-------------|------------|
| Worker Pool | Implement a concurrent worker pool using Goroutines and Channels. | Medium |
| Context Cancellation | Write a function that makes an HTTP request but cancels it if it takes more than 100ms using the `context` package. | Medium |
| Mutex vs Channels | Solve a race condition using both `sync.Mutex` and channels. | Medium |

## Hiring Manager Perspective
"Go is designed to be simple. I look for candidates who write idiomatic Go code without over-engineering. A solid understanding of channels, context, and avoiding Goroutine leaks is crucial."

## AI Interview Coach
**Prompt:**
> "Act as a Go engineering lead. Interview me on Go concurrency patterns, memory allocation, and the usage of the context package. Provide strict feedback on idiomatic Go practices."
