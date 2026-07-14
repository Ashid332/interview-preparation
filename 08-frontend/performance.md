# Frontend Performance Interview Guide

## Overview
Web performance is directly tied to user retention and revenue. Senior frontend interviews dedicate significant time to this topic. You must understand how the browser renders pages (Critical Rendering Path), Core Web Vitals, memory management, and techniques to optimize bundle sizes and network waterfalls.

## Interview Questions

### Question 1: What are Core Web Vitals, and how do you optimize them?
**Difficulty:** Hard | **Frequency:** Very High | **Companies:** Google, Amazon, E-commerce companies

**Excellent Answer:**
Core Web Vitals are user-centric performance metrics defined by Google that directly impact search ranking and user experience. The three main ones are:
1. **LCP (Largest Contentful Paint):** Measures loading performance. The time it takes for the largest image or text block to become visible. 
   - *Optimization:* Optimize images (WebP/AVIF), use CDNs, prioritize crucial resources via `<link rel="preload">`, and implement SSR.
2. **INP (Interaction to Next Paint):** Measures responsiveness (replaced FID). It tracks the latency of all interactions (clicks, key presses).
   - *Optimization:* Break up long JavaScript tasks using `setTimeout` or `requestIdleCallback`, defer non-critical JS execution, use Web Workers for heavy computations.
3. **CLS (Cumulative Layout Shift):** Measures visual stability. It quantifies unexpected layout shifts during the page lifecycle.
   - *Optimization:* Always specify width/height on images and iframes, avoid inserting content dynamically above existing content, use CSS aspect-ratio.

**Common Mistakes:**
- Still talking about outdated metrics like FID without mentioning INP.
- Listing optimizations without mapping them to the specific metric they improve.

### Question 2: Explain the Critical Rendering Path and how you would optimize a page's initial load.
**Difficulty:** Medium | **Frequency:** High | **Companies:** Cloudflare, Vercel, Meta

**Excellent Answer:**
The Critical Rendering Path (CRP) is the sequence of steps the browser takes to convert HTML, CSS, and JS into pixels on the screen:
1. Parse HTML to create the DOM.
2. Parse CSS to create the CSSOM.
3. Combine DOM and CSSOM to create the Render Tree.
4. Layout (calculate exact positions/sizes).
5. Paint (draw pixels to screen).
To optimize initial load, I focus on minimizing the critical resources:
- **CSS:** Extract inline critical CSS for above-the-fold content and load the rest asynchronously.
- **JavaScript:** Scripts block HTML parsing. Use `defer` (executes after parsing, maintains order) or `async` (executes as soon as downloaded) on `<script>` tags.
- **Assets:** Preconnect to important origins, preload critical fonts, and lazy-load off-screen images using `loading="lazy"`.

**Common Mistakes:**
- Not understanding that CSS is render-blocking.
- Confusing `async` and `defer` script behaviors.

## Real-World Applications
- **Media-Heavy Sites:** Implementing aggressive lazy loading, blur-up placeholders, and serving modern image formats based on device capabilities.
- **Complex SPAs:** Utilizing code splitting at the route or component level (e.g., `React.lazy`) to ensure the initial JS bundle is under 150kb.
- **High-Traffic Platforms:** Setting up real user monitoring (RUM) to track performance metrics in the wild, identifying bottlenecks that only occur on low-end devices.

## Practice Problems

| Problem | Focus Area | Difficulty |
|---------|------------|------------|
| Analyze a provided Chrome DevTools Network and Performance trace | Profiling, Bottleneck identification | Hard |
| Optimize a heavily nested, long list of items | Virtualization/Windowing, Memory management | Medium |
| Reduce the bundle size of a Webpack/Vite project | Tree-shaking, Dynamic Imports, Bundle Analyzer | Medium |
| Fix a memory leak in a Single Page Application | Closure scopes, Event Listeners, DevTools Memory tab | Hard |

## Hiring Manager Perspective
"Anyone can build a fast app on an M2 MacBook Pro on gigabit fiber. I want engineers who test their work on 3G throttling and mid-tier Android devices. If a candidate knows how to read a flame chart in Chrome DevTools and can explain the concept of 'Time to Interactive', they instantly stand out."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Web Performance Expert. Present me with a scenario where an e-commerce product page has a terrible Cumulative Layout Shift (CLS) score and poor Largest Contentful Paint (LCP) due to a hero image carousel and dynamic ad banners. Ask me how I would systematically diagnose and fix these issues."
