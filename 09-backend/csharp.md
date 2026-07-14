# C# Backend Interview Guide

## Overview
C# is a modern, object-oriented, and type-safe programming language developed by Microsoft. Paired with the .NET platform, it is extensively used to build enterprise-grade backend services, web applications, and APIs, particularly in environments deeply integrated with Azure.

## Interview Questions

### Q1: Explain how async/await works in C# and what the State Machine is.
**Difficulty:** Hard | **Frequency:** High | **Companies:** Microsoft, Stack Overflow, Electronic Arts
**Excellent Answer:**
The `async` and `await` keywords provide a declarative way to write asynchronous code. When the compiler encounters `await`, it doesn't block the thread. Instead, it generates a hidden State Machine. It captures the context, returns control to the caller, and when the awaited task completes, it resumes execution of the method from where it left off, potentially on a different thread (unless constrained by a SynchronizationContext).
**Common Mistakes:**
- Believing `async` creates a new thread automatically.
- Using `Task.Wait()` or `.Result` in async code, which can cause deadlocks.

## Real-World Applications
- Enterprise web services (.NET Core / ASP.NET).
- Desktop applications (WPF).
- Game development (Unity).
- Cloud-native Azure microservices.

## Practice Problems

| Problem | Description | Difficulty |
|---------|-------------|------------|
| LINQ Queries | Write complex LINQ queries to join, group, and filter in-memory collections efficiently. | Medium |
| Async Deadlocks | Debug a provided C# code snippet that is deadlocking due to incorrect async usage. | Hard |
| Dependency Injection | Set up scoped, transient, and singleton services in an ASP.NET Core application. | Easy |

## Hiring Manager Perspective
"I look for developers who understand the internals of .NET Core, can write efficient LINQ queries, and know how to structure a clean, testable architecture using Dependency Injection. Misunderstanding async/await is a massive red flag."

## AI Interview Coach
**Prompt:**
> "Act as a .NET Architect interviewing me. Ask me about garbage collection in .NET, Entity Framework performance tuning, and the internal workings of async/await."
