# Vue.js Interview Guide

## Overview
Vue.js is known for its gentle learning curve, reactivity system, and the powerful Composition API. Interviews focus on understanding reactivity (how Vue tracks dependencies), component communication, lifecycle hooks, and architectural patterns using the Composition API vs. the Options API.

## Interview Questions

### Question 1: How does Vue's reactivity system work under the hood? (Vue 3)
**Difficulty:** Hard | **Frequency:** High | **Companies:** GitLab, Apple, Alibaba

**Excellent Answer:**
In Vue 3, reactivity is powered by JavaScript `Proxy` objects (replacing Vue 2's `Object.defineProperty`).
When a reactive object is created (via `reactive` or `ref`), Vue wraps it in a Proxy. 
- **Get (Track):** When a property is accessed during a component's render, the Proxy's `get` trap is triggered. Vue tracks the active effect (the render function or a watcher) that accessed this property, adding it to a dependency list.
- **Set (Trigger):** When the property is mutated, the Proxy's `set` trap is triggered. Vue looks up all the effects that depend on this property and re-runs them, updating the DOM.
This Proxy-based approach allows Vue to detect property additions/deletions and array index mutations, which were limitations in Vue 2.

**Common Mistakes:**
- Confusing Vue 2's reactivity (`defineProperty`) with Vue 3's (`Proxy`).
- Not understanding the difference between `ref` (for primitives/reassignment) and `reactive` (for deep object reactivity).

### Question 2: What are the differences between the Options API and the Composition API? Why was the Composition API introduced?
**Difficulty:** Medium | **Frequency:** Very High | **Companies:** Tencent, Nintendo, Adobe

**Excellent Answer:**
- **Options API:** Organizes code by properties (`data`, `methods`, `computed`, `watch`). It's intuitive for small components but can lead to fragmented logic in large components (a feature's logic is scattered across different options).
- **Composition API:** Introduced in Vue 3, it allows organizing code by logical concern. You define logic within a `setup()` function using imported functions like `ref` and `computed`.
**Why it was introduced:** 
1. **Code Organization:** Related logic can be grouped together, making complex components much easier to read and maintain.
2. **Reusability:** It allows for extracting reusable logic into "Composables" (similar to React Hooks), replacing the problematic Mixins pattern which suffered from namespace collisions and unclear property origins.
3. **TypeScript:** The Composition API offers vastly superior TypeScript inference.

**Common Mistakes:**
- Claiming the Options API is deprecated (it is not; they coexist).
- Failing to mention "Composables" as the primary mechanism for code reuse.

## Real-World Applications
- **Progressive Enhancement:** Dropping Vue into a legacy application to add reactive islands of interactivity without rewriting the entire frontend.
- **Complex SPAs:** Building highly interactive applications using Vue Router and Pinia (the modern standard for Vue state management).
- **Static Sites / SSR:** Using Nuxt.js (Vue's meta-framework equivalent to Next.js) for high-performance, SEO-friendly applications.

## Practice Problems

| Problem | Focus Area | Difficulty |
|---------|------------|------------|
| Build a reusable `useMouse` composable | Composition API, Event Listeners | Easy |
| Implement a complex Form with validation | Two-way binding (`v-model`), computed properties | Medium |
| Create a custom directive for lazy loading images | Custom Directives, Intersection Observer | Hard |
| Migrate a component from Options API to Composition API | Refactoring, Reactivity | Medium |

## Hiring Manager Perspective
"Vue developers often transition quickly, but the best ones understand the underlying mechanisms. I look for developers who write clean, modular Composables and know exactly when to use `watch` versus `computed`. A solid grasp of Pinia and Nuxt.js is often required for our enterprise projects."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Senior Vue.js Engineer conducting a technical interview. Provide me with a Vue 3 component written in the Options API that has several reactivity bugs and poor code reuse. Ask me to refactor it using `<script setup>`, the Composition API, and Composables, and explain my design choices."
