# Data Science Case Studies

## Overview
Case study interviews evaluate your product sense and problem-solving framework. You are given an ambiguous business problem ("How do we increase engagement?") and must break it down into measurable metrics, hypotheses, data analyses, and modeling approaches.

## Interview Questions

### Q1: How would you measure the success of a new 'Stories' feature on our app?
**Difficulty:** Hard | **Frequency:** High | **Companies:** Meta, Snap, TikTok

**Excellent Answer:**
I would break this down into three categories of metrics:
1. **Adoption/Usage:** How many users are using it? Metrics: % of DAU interacting with Stories, average number of stories viewed/posted per user per day.
2. **Engagement/Impact on Core:** Does this cannibalize other features? Metrics: Total time spent in app, change in engagement with the main feed. We want to ensure total engagement is additive.
3. **Retention/Downstream:** Does it keep users coming back? Metrics: D7 and D30 retention of users who use Stories vs. those who don't (measured via A/B test to prove causality).
I would design an A/B test holding out the feature for 5% of users to measure true incremental lift on core company metrics.

**Common Mistakes:**
- Suggesting a machine learning model right away when a simple analysis or A/B test is needed.
- Forgetting to mention counter-metrics or cannibalization.

## Real-World Applications
- Investigating why ride cancellations spiked in a specific city.
- Designing the pricing strategy for a new subscription tier.

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Metric Drop | DAU dropped by 10% yesterday. How do you investigate? | Hard | [Link](#) |
| Feature Launch | Should we launch a feature if it increases engagement but drops revenue? | Medium | [Link](#) |

## Hiring Manager Perspective
Case studies are where candidates shine or fail. I am looking for structured thinking. Do they clarify the goal first? Do they state their assumptions? Do they define clear, actionable metrics rather than vague vanity metrics?

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Give me a product case study interview question typical of Meta or Google. Act as the interviewer and evaluate my framework."
- "What is a good framework for answering root-cause analysis questions (e.g., 'Metrics dropped by X%')?"
