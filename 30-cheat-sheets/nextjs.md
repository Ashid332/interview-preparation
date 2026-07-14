# Next.js Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| App Router | Modern Next.js routing system based on React Server Components, layout sharing, and nested routing. |
| Server Components (RSC) | Components that render on the server by default, shipping zero JS to the client. |
| SSR / SSG / ISR | Server-Side Rendering (per request), Static Site Generation (build time), Incremental Static Regeneration. |
| Routing | File-system based routing (e.g., `app/page.tsx`, `app/dashboard/page.tsx`). |

## Must-Know Items
- Differences between Server Components and Client Components (`"use client"`).
- Data fetching strategies (`fetch` with caching vs dynamic rendering).
- Route handlers (`app/api/route.ts`).
- Middleware for edge-level request modification.

## Common Interview Questions (Quick)
1. What is the difference between App Router and Pages Router?
2. When should you use a Client Component vs a Server Component?
3. How does Incremental Static Regeneration (ISR) work?
4. How do you handle authentication in Next.js?

## Critical Commands/Patterns
```tsx
// Server Component Data Fetching (Next.js 13+)
export default async function Page() {
  const data = await fetch('https://api.example.com/data', { 
    next: { revalidate: 3600 } // ISR pattern
  }).then(res => res.json());

  return <div>{data.title}</div>;
}
```

## Decision Framework
- **RSC vs Client Component:** Default to RSC. Use Client Components ONLY when you need interactivity (`onClick`), hooks (`useState`), or browser APIs.
- **Rendering Strategy:** Static rendering for blogs/marketing (fastest). Dynamic rendering for personalized user dashboards.

## Common Mistakes
- Using `"use client"` at the root layout, turning the whole app into client-side rendering.
- Leaking sensitive environment variables to the client (must use `NEXT_PUBLIC_` prefix for client).
- Fetching data in client components unnecessarily when it could be fetched on the server.

## One-Minute Review
- Next.js is a full-stack React framework. Understand the paradigm shift to Server Components, file-system routing, and built-in optimizations (images, fonts, scripts).
