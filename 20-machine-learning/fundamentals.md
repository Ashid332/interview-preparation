# Machine Learning Fundamentals

## Overview
Machine Learning fundamentals cover the core theoretical concepts that underpin all algorithms. These include the bias-variance tradeoff, overfitting, underfitting, cross-validation, and regularizations. A strong grasp of these concepts is essential to demonstrate you understand the mechanics behind model training and generalization.

## Interview Questions

### Q1: Explain the Bias-Variance Tradeoff.
**Difficulty:** Medium | **Frequency:** Very High | **Companies:** Meta, Apple, Netflix, Google

**Excellent Answer:**
The bias-variance tradeoff is the tension between the error introduced by the bias and the error introduced by the variance. 
- **Bias** is the error from erroneous assumptions in the learning algorithm. High bias can cause an algorithm to miss the relevant relations between features and target outputs (underfitting).
- **Variance** is the error from sensitivity to small fluctuations in the training set. High variance can cause an algorithm to model the random noise in the training data, rather than the intended outputs (overfitting).
The goal is to find the sweet spot that minimizes total error by balancing bias and variance, often achieved through techniques like regularization or ensemble methods.

**Common Mistakes:**
- Confusing bias with statistical bias or prejudice.
- Stating that we can minimize both simultaneously without trade-offs.

## Real-World Applications
- Tuning hyperparameters of a Random Forest to prevent it from memorizing the training data.
- Deciding whether to collect more training data (helps with high variance) or add more features (helps with high bias).

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Learning Curves | Diagnose high bias vs high variance from learning curves | Easy | None |
| Regularization Impact | Apply L1/L2 and observe the effect on bias/variance | Medium | None |

## Hiring Manager Perspective
Candidates must be able to diagnose a poorly performing model. If a model is overfitting, what steps should they take? If they don't understand bias and variance, they will waste time trying the wrong solutions (like adding more data when the model has high bias).

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Explain the bias-variance tradeoff using a simple real-world analogy."
- "Act as an interviewer and ask me follow-up questions about how to handle a model that is severely overfitting the training data."
