# Frontend Engineer Interview Learning Path

## Role Overview
Frontend Engineers specialize in building user-facing interfaces, ensuring performance, accessibility, and exceptional user experiences. This role demands deep knowledge of JavaScript/TypeScript, DOM manipulation, framework ecosystems (React/Vue/Angular), and frontend system design. This 10-week path targets high-impact frontend roles.

## Prerequisites

| Skill Area | Expected Proficiency Level | Resources for Review |
|------------|----------------------------|----------------------|
| HTML/CSS | Advanced | MDN Web Docs, CSS Tricks |
| JavaScript | Advanced (ES6+, Closures, Promises) | You Don't Know JS |
| Web Framework | Intermediate (React/Vue) | Official Framework Documentation |

## Path Overview

```mermaid
gantt
    title Frontend Engineer 10-Week Preparation Plan
    dateFormat  w
    axisFormat %W
    section Core Web Tech
    HTML/CSS & Vanilla JS :a1, 0, 3w
    section Framework & State
    Frameworks & State Mgmt :a2, after a1, 3w
    section System Design
    Frontend Architecture :a3, after a2, 2w
    section Behavioral & Polish
    Mock Interviews       :a4, after a3, 2w
```

## Weekly Roadmap

### Weeks 1-3: Core Web Technologies & Vanilla JavaScript
Focus on the foundational building blocks of the web and DOM manipulation.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 1 | Advanced HTML/CSS | Accessibility (a11y), Flexbox/Grid, Responsive Design | Build 3 complex layouts without a framework |
| 2 | Vanilla JS Fundamentals | Hoisting, Closures, Prototypal Inheritance, `this` | Implement Polyfills (Map, Reduce, Bind) |
| 3 | DOM & Async JS | Event Delegation, Promises, Async/Await, Debounce/Throttle | Build a typeahead widget in Vanilla JS |

### Weeks 4-6: Framework Ecosystem & State Management
Deep dive into modern frontend frameworks and application state.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 4 | Framework Mechanics | Virtual DOM, Component Lifecycle, Hooks/Reactivity | Rebuild a framework primitive (e.g., `useState`) |
| 5 | State Management | Redux, Context API, Zustand, Flux Pattern | Build a global state managed Shopping Cart |
| 6 | Performance & Web APIs | Critical Rendering Path, Web Workers, Intersection Observer | Audit and optimize an existing web app via Lighthouse |

### Weeks 7-8: Frontend System Design
Designing complex client-side applications.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 7 | Component Architecture | Component Libraries, Micro-frontends, Data Fetching | Design a News Feed (e.g., Facebook Feed) |
| 8 | Networking & Security | REST/GraphQL, WebSockets, XSS, CSRF, CORS | Design an Auto-saving Collaborative Editor |

### Weeks 9-10: Behavioral & Mock Interviews
Refining presentation and cultural fit.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 9 | Behavioral (STAR) | Cross-functional collaboration, technical disagreements | Draft 8 STAR stories focused on UI/UX challenges |
| 10 | Mock Interviews | Whiteboarding UI architectures, coding under pressure | Conduct 3 frontend-specific mock interviews |

## Milestones & Checkpoints

- [ ] **End of Week 3:** Can implement generic utility functions (debounce, deep clone) from scratch in < 15 minutes.
- [ ] **End of Week 6:** Can explain exactly how your framework of choice batches updates and reconciles the DOM.
- [ ] **End of Week 8:** Can whiteboard a component hierarchy and API contract for a complex web application.
- [ ] **End of Week 10:** Confidently articulate tradeoffs between client-side vs server-side rendering (CSR vs SSR).

## Company Recommendations

- **Product-Led Companies (Airbnb, Vercel):** Expect heavy emphasis on pixel-perfection, performance, and accessibility.
- **Enterprise SaaS (Salesforce, Atlassian):** Focus on complex state management, scalable component architectures, and legacy system integration.
- **Early Stage Startups:** Be prepared to discuss setting up frontend pipelines (Webpack/Vite) from scratch and rapid prototyping.

## Interview Readiness Checklist

- [ ] Understand the Critical Rendering Path and how to optimize it.
- [ ] Can write a generic polyfill for `Promise.all` without looking at reference material.
- [ ] Framework system design structure memorized (Requirements -> Data Model -> Component Tree -> API -> Performance).
- [ ] Comfortable discussing accessibility standards (WCAG).
