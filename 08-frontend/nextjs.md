# Next.js Interview Guide

## Overview
Next.js is the industry standard for production-ready React applications. It provides hybrid static and server rendering, smart bundling, route pre-fetching, and more. Interviews will test your understanding of rendering strategies (SSR, SSG, ISR, CSR), routing (App Router vs Pages Router), and performance optimizations like Image and Font components.

## Interview Questions

### Question 1: What is the difference between SSR, SSG, and ISR in Next.js, and when would you use each?
**Difficulty:** Medium | **Frequency:** Very High | **Companies:** Vercel, Netflix, TikTok

**Excellent Answer:**
- **SSG (Static Site Generation):** HTML is generated at *build time*. This is the fastest and most SEO-friendly option. I use it for marketing pages, blogs, and documentation where data doesn't change on every request.
- **SSR (Server-Side Rendering):** HTML is generated on *each request*. This ensures data is always up-to-date and SEO is maintained. I use it for personalized dashboards or pages with highly dynamic data that must be indexed.
- **ISR (Incremental Static Regeneration):** Combines the benefits of SSG and SSR. Pages are built statically, but can be updated in the background at specific intervals without rebuilding the whole site. I use this for e-commerce product pages where data changes occasionally but fast load times are critical.

**Common Mistakes:**
- Recommending SSR for everything, ignoring the server cost and TTFB (Time to First Byte) latency.
- Confusing CSR (Client-Side Rendering) with SSG.

### Question 2: Explain the shift from the Pages Router to the App Router in Next.js. What are Server Components?
**Difficulty:** Hard | **Frequency:** High | **Companies:** OpenAI, Stripe, Spotify

**Excellent Answer:**
The App Router represents a paradigm shift leveraging React Server Components (RSC). 
In the Pages router, data fetching was tied to the page level (`getServerSideProps`), and all components were hydrated on the client.
With the App Router and RSC:
1. Components run on the server by default, meaning their JavaScript is *never* sent to the client, reducing bundle size.
2. You can fetch data directly within asynchronous server components.
3. You explicitly opt-in to client-side interactivity using the `"use client"` directive at the top of a file.
This separation allows for heavy backend operations (like database queries) to occur securely and directly in UI components without exposing APIs, while keeping the client bundle exceptionally small.

**Common Mistakes:**
- Thinking `"use client"` means the component is only rendered on the client (it is still server-rendered to HTML for initial load, then hydrated).
- Trying to use React Hooks (like `useState`) inside Server Components.

## Real-World Applications
- **E-commerce:** Using ISR to serve thousands of product pages rapidly while keeping pricing and inventory relatively fresh.
- **SEO-Heavy Web Apps:** Leveraging SSR and Next.js's metadata API for complex, dynamic SEO tags for news outlets or job boards.
- **Full-stack Applications:** Using Next.js Route Handlers and Server Actions to build end-to-end applications without setting up a separate Express backend.

## Practice Problems

| Problem | Focus Area | Difficulty |
|---------|------------|------------|
| Migrate a page from `getServerSideProps` to App Router | App Router, Data Fetching | Medium |
| Implement a search bar with URL query state | Client Components, Routing | Easy |
| Build an authenticated route using Middleware | Next.js Middleware, Auth | Hard |
| Optimize a slow page utilizing `next/image` and dynamic imports | Performance, Web Vitals | Medium |

## Hiring Manager Perspective
"When interviewing for a Next.js role, I want to know if the candidate understands *why* we use Next.js instead of vanilla React. They should be deeply familiar with the trade-offs of different rendering strategies and understand how to optimize Core Web Vitals to deliver a blazing-fast user experience."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Vercel Solutions Architect. I am designing a large-scale e-commerce platform using Next.js. Ask me architectural questions about caching strategies, routing, and rendering choices (App Router). Challenge my decisions on performance and SEO."
