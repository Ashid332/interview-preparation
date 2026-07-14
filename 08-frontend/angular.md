# Angular Interview Guide

## Overview
Angular is an enterprise-grade, opinionated framework maintained by Google. It provides a complete solution for building large-scale applications out of the box. Interviews focus heavily on TypeScript, RxJS, Dependency Injection, component architecture, performance (Change Detection), and module management.

## Interview Questions

### Question 1: How does Change Detection work in Angular? Explain `OnPush` strategy.
**Difficulty:** Hard | **Frequency:** Very High | **Companies:** Google, Microsoft, Morgan Stanley

**Excellent Answer:**
Angular's default change detection checks every component in the component tree whenever any event, timer, or XHR resolves (powered by Zone.js). It compares current template bindings with their previous values.
For large apps, this default behavior is terrible for performance.
To optimize, we use the `ChangeDetectionStrategy.OnPush`. When a component is set to `OnPush`, Angular only runs change detection for that component if:
1. Its input properties (`@Input`) change by *reference*.
2. An event originates from the component or its children.
3. An Observable linked via the `async` pipe emits a new value.
4. We manually trigger it using `ChangeDetectorRef.markForCheck()`.
Using `OnPush` combined with immutable data structures and RxJS observables is critical for performant Angular applications.

**Common Mistakes:**
- Not understanding that `OnPush` relies on reference equality.
- Mutating an object passed as an `@Input` and wondering why the view doesn't update.

### Question 2: What is Dependency Injection (DI) in Angular, and how do you configure providers?
**Difficulty:** Medium | **Frequency:** High | **Companies:** IBM, Cisco, Enterprise companies

**Excellent Answer:**
Dependency Injection is a core design pattern in Angular where classes request dependencies from external sources rather than creating them. This promotes modularity and makes unit testing easier (mocking).
Angular’s DI framework provides instances (services) to components. You can configure providers at different levels:
1. **`providedIn: 'root'`**: Creates a single, shared instance (singleton) across the entire application. It also enables tree-shaking if the service is never injected.
2. **Component level (`providers: [...]`)**: Creates a new instance of the service every time the component is created. The service is destroyed when the component is destroyed.
3. **Module level**: (Historically used, though standalone components are changing this pattern) Scoped to a specific feature module.

**Common Mistakes:**
- Putting all services in component providers, unintentionally creating multiple instances and losing shared state.
- Failing to mention tree-shaking benefits of `providedIn: 'root'`.

## Real-World Applications
- **Enterprise SaaS:** Building complex dashboards with hundreds of forms, utilizing Angular's robust Reactive Forms module.
- **Financial Applications:** Applications requiring strict type safety, predictable state changes, and robust architecture, often leveraging NgRx for state management.
- **Large Monorepos:** Angular CLI and strict structure make it ideal for large teams working across multiple projects in tools like Nx.

## Practice Problems

| Problem | Focus Area | Difficulty |
|---------|------------|------------|
| Build a Typeahead search using RxJS | RxJS (`switchMap`, `debounceTime`), Async Pipe | Medium |
| Implement a custom Async Validator for a Reactive Form | Reactive Forms, HTTP interceptors | Hard |
| Create a component that implements `ControlValueAccessor` | Custom form controls, Interfaces | Hard |
| Refactor a slow component to use `OnPush` change detection | Performance, Immutability | Medium |

## Hiring Manager Perspective
"Angular is opinionated, and we expect candidates to know 'the Angular way.' A strong candidate must be highly proficient in RxJS—understanding operators like `switchMap`, `mergeMap`, and `exhaustMap` is non-negotiable. I also look for modern Angular knowledge, specifically the transition to Standalone Components and Signals."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Principal Angular Developer. Ask me a complex scenario question involving an RxJS memory leak and race conditions when fetching data in an Angular component. Evaluate my proposed solution, specifically looking for best practices using the `async` pipe or `takeUntil` operators."
