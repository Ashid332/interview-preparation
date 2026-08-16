# Machine Learning Algorithms

## Overview
Interviewers frequently ask about the inner workings of popular ML algorithms to ensure you aren't just treating them as black boxes. You need to understand how algorithms like Linear Regression, Decision Trees, Random Forests, SVMs, and Gradient Boosting algorithms work mathematically and intuitively.

## Interview Questions

### Q1: How does a Random Forest work, and why is it better than a single Decision Tree?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Amazon, Uber, Microsoft

**Excellent Answer:**
A Random Forest is an ensemble learning method that constructs a multitude of decision trees at training time and outputs the mode of the classes (classification) or mean prediction (regression) of the individual trees. It improves upon a single decision tree by mitigating overfitting. It does this through two types of randomness: 
1. **Bagging (Bootstrap Aggregating):** Each tree is trained on a random sample of the data with replacement.
2. **Feature Randomness:** At each split in the tree, a random subset of features is considered.
This decorrelates the trees, so when their predictions are averaged, the variance is significantly reduced without a substantial increase in bias.

**Common Mistakes:**
- Forgetting to mention feature sampling (only mentioning bagging).
- Claiming Random Forests cannot overfit (they can, just less easily than single trees).

## Real-World Applications
- Predicting customer churn based on multiple demographic and behavioral features.
- Credit scoring models where non-linear relationships exist but some interpretability is needed.

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Implement Tree | Write a simple decision tree split function from scratch | Hard | None |
| Algorithm Comparison | Compare SVM and Logistic Regression decision boundaries | Medium | None |

## Hiring Manager Perspective
I want to know if the candidate understands the assumptions and limitations of the algorithm. Do they know that tree-based models don't extrapolate well outside the training data range? Do they know when to scale features (e.g., for SVMs or KNNs) versus when it's not strictly necessary (e.g., for tree-based models)?

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Quiz me on the assumptions of Linear Regression, Logistic Regression, and SVMs."
- "Act as an interviewer. Ask me to explain Gradient Boosting to a non-technical stakeholder."
