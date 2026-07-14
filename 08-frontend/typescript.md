# TypeScript Interview Guide

## Overview
TypeScript adds static typing to JavaScript, improving developer experience, code maintainability, and scalability. Interviews focus on your ability to use types effectively to prevent runtime errors, understanding advanced types (Generics, Utility Types, Conditional Types), and knowing when to use Interfaces vs. Types.

## Interview Questions

### Question 1: What is the difference between `interface` and `type` in TypeScript? When would you use one over the other?
**Difficulty:** Easy | **Frequency:** High | **Companies:** Microsoft, Slack, Airbnb

**Excellent Answer:**
Both `interface` and `type` can describe the shape of an object, but they have subtle differences:
1. **Extensibility:** Interfaces are extendable using the `extends` keyword and support *declaration merging* (defining the same interface multiple times merges them). Types are extendable via intersections (`&`), but do not support declaration merging.
2. **Capabilities:** `type` (Type Aliases) can represent primitives, unions, and tuples, which interfaces cannot. 
**When to use:** I use `interface` when defining the shape of objects, especially public APIs or class contracts, because of better error messages and declaration merging. I use `type` for unions, intersections, primitives, or complex utility types.

**Common Mistakes:**
- Saying they are exactly the same.
- Not knowing about declaration merging.

### Question 2: Explain Generics and write a generic function that merges two objects.
**Difficulty:** Medium | **Frequency:** High | **Companies:** Uber, Lyft, Stripe

**Excellent Answer:**
Generics allow us to create reusable components that can work over a variety of types rather than a single one, providing type safety without losing information.
Here is a generic function to merge two objects:
```typescript
function merge<T extends object, U extends object>(obj1: T, obj2: U): T & U {
  return { ...obj1, ...obj2 };
}
```
By using `<T extends object, U extends object>`, we constrain the generic types to be objects. The return type is an intersection `T & U`, ensuring TypeScript knows the resulting object contains properties from both.

**Common Mistakes:**
- Using `any` instead of Generics, which defeats the purpose of TypeScript.
- Failing to use constraints (`extends`) when the generic type requires specific properties.

## Real-World Applications
- **API Responses:** Strongly typing API responses so the frontend knows exactly what fields are available, reducing runtime `undefined` errors.
- **Component Libraries:** Building reusable React/Vue components with generic props (e.g., a Dropdown component that accepts an array of any type `T` and strongly types the `onSelect` callback).
- **State Management:** Typing Redux or Zustand stores to ensure dispatched actions match their payloads.

## Practice Problems

| Problem | Focus Area | Difficulty |
|---------|------------|------------|
| Implement the `Omit<T, K>` utility type | Mapped types, conditional types | Medium |
| Create a deep readonly type `DeepReadonly<T>` | Recursive types, Mapped types | Hard |
| Type an Event Emitter | Generics, Index Signatures | Medium |
| Write a type-safe `get` function for object paths | Template Literal Types, Recursion | Hard |

## Hiring Manager Perspective
"I look for developers who use TypeScript to help the team, not hinder it. Over-engineering types to the point where they are unreadable, or relying too heavily on `any` and `@ts-ignore`, are red flags. A great TS developer writes self-documenting types that catch business logic errors at compile time."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a strict TypeScript interviewer. Give me a scenario where I need to write an advanced generic type or use conditional types to solve a type-safety issue in a mock application. Evaluate my solution based on type strictness and readability."
