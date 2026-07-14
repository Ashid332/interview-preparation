# Frontend Engineering Interviews

## Overview
Frontend engineering interviews assess your ability to build user interfaces, manage state, optimize performance, and ensure accessibility. They go beyond simple HTML/CSS and delve deeply into JavaScript/TypeScript fundamentals, framework-specific knowledge (React, Vue, Angular), and system design for web applications.

## Interview Questions

### Question 1: How do you design a scalable frontend architecture for a large web application?
**Difficulty:** Hard | **Frequency:** High | **Companies:** Meta, Google, Amazon, Netflix

**Excellent Answer:**
A scalable frontend architecture requires a modular, maintainable, and performant foundation. I would start by adopting a component-driven framework like React or Vue, breaking the UI into reusable, isolated components. 
1. **State Management:** Use a scalable state management solution (e.g., Redux Toolkit, Zustand, or React Context) ensuring separation of UI state and server state (using tools like React Query or Apollo).
2. **Code Organization:** Adopt a feature-based folder structure rather than a type-based one.
3. **Performance:** Implement code splitting, lazy loading, and asset optimization. Use SSR (Next.js) or SSG where SEO and initial load times are critical.
4. **Testing:** Set up a robust testing pyramid: unit tests (Jest/Vitest), component tests (React Testing Library), and E2E tests (Cypress/Playwright).
5. **CI/CD:** Automate linting, testing, and deployments with GitHub Actions.

**Common Mistakes:**
- Focusing only on the UI and ignoring data flow/state management.
- Neglecting performance considerations like bundle size and network waterfalls.
- Failing to mention testing and CI/CD pipelines.

## Real-World Applications
Frontend engineering is critical in applications like:
- **Single Page Applications (SPAs):** Dashboards, productivity tools (e.g., Notion, Figma) where seamless interaction without page reloads is essential.
- **E-commerce:** High-performance, SEO-optimized storefronts requiring fast load times and reliable state management for carts.
- **Streaming Platforms:** Applications managing complex video playback states, real-time data, and cross-device compatibility (e.g., Netflix web client).

## Practice Problems

| Problem | Focus Area | Difficulty |
|---------|------------|------------|
| Build a Typeahead/Autocomplete Widget | Debouncing, API integration, Accessibility | Medium |
| Implement an Image Carousel | State management, CSS transitions, DOM manipulation | Easy |
| Design a File Explorer UI | Recursion, component design, state management | Hard |
| Create a Virtualized List | Performance optimization, DOM recycling | Hard |

## Hiring Manager Perspective
"When interviewing frontend engineers, I look for a balance between visual polish and robust engineering. I want candidates who understand *how* a framework works under the hood, not just how to use its APIs. A strong candidate always considers edge cases, accessibility, and performance before writing a single line of code."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Senior Frontend Engineering Manager at a Big Tech company. Ask me a system design question about building the frontend architecture for a real-time collaborative document editor like Google Docs. Wait for my response, then evaluate my approach based on performance, state management, and scalability."
