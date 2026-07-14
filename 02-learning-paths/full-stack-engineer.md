# Full-Stack Engineer Interview Learning Path

## Role Overview
Full-Stack Engineers bridge the gap between frontend interfaces and backend infrastructure. This role demands versatility, an understanding of the end-to-end web architecture, and the ability to seamlessly integrate UI components with RESTful/GraphQL APIs. This 12-week path prepares you for robust end-to-end product engineering roles.

## Prerequisites

| Skill Area | Expected Proficiency Level | Resources for Review |
|------------|----------------------------|----------------------|
| Web Fundamentals | Intermediate (HTML, CSS, JS) | MDN Web Docs |
| Backend Language | Intermediate (Node.js, Python, Go, Ruby) | Language documentation |
| Database Basics | Intermediate (SQL, basic ORMs) | SQL Tutorials |

## Path Overview

```mermaid
gantt
    title Full-Stack Engineer 12-Week Preparation Plan
    dateFormat  w
    axisFormat %W
    section Frontend
    UI & State Mgmt       :a1, 0, 3w
    section Backend
    APIs & Databases      :a2, after a1, 3w
    section Integration
    E2E & System Design   :a3, after a2, 3w
    section Behavioral & Polish
    Mock Interviews       :a4, after a3, 3w
```

## Weekly Roadmap

### Weeks 1-3: Frontend Mastery
Solidifying user interface construction and client-side logic.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 1 | DOM & React/Vue | Components, Hooks, State Management, Virtual DOM | Build an interactive Kanban board |
| 2 | Advanced JS | Asynchronous programming, Event Loop, Closures | Implement a generic `fetch` wrapper with retries |
| 3 | Performance & CSS | Responsive design, CSS Modules/Tailwind, Lighthouse optimization | Optimize a slow-loading web page |

### Weeks 4-6: Backend & API Mastery
Building robust, secure, and scalable server-side logic.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 4 | API Design | REST vs GraphQL, Middleware, Authentication (JWT, OAuth) | Build a secure REST API with user auth |
| 5 | Databases & ORMs | SQL querying, indexing, migrations, Active Record/Prisma | Design a schema for an E-commerce platform |
| 6 | Caching & Scale | Redis, basic load balancing, background jobs | Add Redis caching and background email workers to an API |

### Weeks 7-9: End-to-End System Design
Tying the frontend and backend together.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 7 | Full-Stack Architecture| Monolith vs Microservices, SSR vs CSR vs SSG | Design an application like Instagram (App + API) |
| 8 | Cloud & Deployment | Docker basics, CI/CD pipelines, Vercel/Heroku/AWS | Containerize an app and write a GitHub Action |
| 9 | Security & Testing | XSS, CSRF, CORS, Unit vs Integration vs E2E Testing | Write Cypress/Playwright tests for a critical user flow |

### Weeks 10-12: Behavioral & Mock Interviews
Perfecting the holistic product narrative.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 10 | Behavioral (STAR) | Product ownership, cross-stack debugging, scoping | Draft 8 STAR stories on end-to-end delivery |
| 11 | Mock Interviews (Coding)| Context switching between UI and Backend in technical rounds | Conduct 2 full-stack specific coding mocks |
| 12 | System Design & Polish | Articulating full-stack trade-offs | Conduct 2 System Design mocks |

## Milestones & Checkpoints

- [ ] **End of Week 3:** Can build a functional, responsive SPA fetching data from a mock API in under 2 hours.
- [ ] **End of Week 6:** Can design a normalized database schema and expose it securely via RESTful endpoints.
- [ ] **End of Week 9:** Can confidently discuss how a button click on the client propagates through the load balancer, API, and database.
- [ ] **End of Week 11:** Able to switch paradigms (e.g., from CSS Flexbox to SQL joins) smoothly during an interview.

## Company Recommendations

- **Startups (Seed to Series C):** Huge demand for Full-Stack. Emphasize speed of delivery, pragmatic architecture choices, and product sense.
- **Agency / Consultancies:** Focus heavily on versatility, client communication, and setting up new projects rapidly.
- **Enterprise (Microsoft, Amazon):** Full-stack roles might lean heavier toward one side (e.g., 70% backend, 30% frontend). Tailor your prep to the job description.

## Interview Readiness Checklist

- [ ] Can bootstrap a full-stack environment (e.g., Next.js + Prisma or Node + React) in < 10 mins.
- [ ] Clear understanding of Web security fundamentals (CORS, JWTs, Session Cookies).
- [ ] Can articulate the trade-offs between Server-Side Rendering (SSR) and Client-Side Rendering (CSR).
- [ ] Prepared to discuss a complex bug you traced from the frontend down to the database level.
