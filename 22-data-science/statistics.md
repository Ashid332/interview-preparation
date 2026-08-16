# Statistics & Probability

## Overview
Statistics and probability are the backbone of data science. You will be tested on combinations/permutations, expected value, probability distributions, hypothesis testing, A/B testing, and confidence intervals.

## Interview Questions

### Q1: Explain the p-value to a non-technical person.
**Difficulty:** Medium | **Frequency:** High | **Companies:** Google, Spotify, Airbnb

**Excellent Answer:**
Imagine we are testing a coin to see if it's rigged. We assume it's a normal, fair coin (this is our null hypothesis). We flip it 10 times, and it lands on heads all 10 times. 
The p-value is the probability of getting this exact result (10 heads) or something even more extreme, *assuming the coin is actually fair*. 
Since getting 10 heads in a row with a fair coin is extremely unlikely (less than 0.1%), the p-value is very low. This low p-value tells us that our initial assumption (the coin is fair) is probably wrong, so we conclude the coin is rigged. In business, it helps us determine if a change we made actually caused an improvement, or if we just got lucky.

**Common Mistakes:**
- Saying it's "the probability that the null hypothesis is true" (this is statistically incorrect).
- Overcomplicating the answer with jargon.

## Real-World Applications
- Determining if a new button color actually increases click-through rates (A/B testing).
- Modeling the number of customer arrivals per hour using a Poisson distribution.

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Bayes Theorem | Solve a medical testing probability problem | Medium | None |
| A/B Test Sizing | Calculate the required sample size for an A/B test | Hard | None |

## Hiring Manager Perspective
We want to see that candidates won't misinterpret experimental results. A data scientist who doesn't understand statistical significance might recommend launching a feature based on noise, costing the company millions.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Give me 3 probability brain teasers commonly asked in data science interviews."
- "Explain the Central Limit Theorem and why it is important for A/B testing."
