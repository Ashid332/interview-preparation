# Data Scientist Interview Learning Path

## Role Overview
Data Scientists analyze complex datasets to inform business decisions, design rigorous experiments, and build predictive models. The role varies wildly by company, but generally requires a mix of statistics, programming, product sense, and machine learning. This 12-week path prepares you for full-stack Data Science interviews.

## Prerequisites

| Skill Area | Expected Proficiency Level | Resources for Review |
|------------|----------------------------|----------------------|
| SQL | Advanced | Mode SQL Tutorial, LeetCode DB |
| Math & Statistics | Advanced (Probability, Testing) | "Practical Statistics for Data Scientists" |
| Python / R | Intermediate (Pandas, Scikit-learn) | Python Data Science Handbook |

## Path Overview

```mermaid
gantt
    title Data Scientist 12-Week Preparation Plan
    dateFormat  w
    axisFormat %W
    section SQL & Coding
    Data Manipulation     :a1, 0, 3w
    section Stats & Exp
    A/B Testing & Stats   :a2, after a1, 3w
    section Modeling
    Machine Learning      :a3, after a2, 4w
    section Product Case
    Business Sense & Mocks:a4, after a3, 2w
```

## Weekly Roadmap

### Weeks 1-3: Advanced SQL & Data Manipulation
The bread and butter of data science interviews.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 1 | SQL Fundamentals | Joins, Aggregations, Grouping, Having | 20 LeetCode/StrataScratch Medium SQL |
| 2 | Advanced SQL | Window Functions, CTEs, Self-Joins, Date manipulation | 15 Hard SQL problems |
| 3 | Python/Pandas Data Wrangling| Dataframes, Merging, Missing values, Vectorized operations | Solve Titanic/Kaggle dataset using only Pandas |

### Weeks 4-6: Statistics & A/B Testing
Rigorous experimental design and statistical inference.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 4 | Probability Theory | Bayes' Theorem, Distributions (Normal, Binomial, Poisson) | Solve 20 probability interview questions |
| 5 | Hypothesis Testing | P-values, Confidence Intervals, T-tests, Z-tests | Conduct a manual hypothesis test in Python |
| 6 | A/B Testing Design | Sample size calculation, Minimum Detectable Effect, Network Effects | Design an A/B test for a new UI feature |

### Weeks 7-10: Predictive Modeling & Machine Learning
Applying algorithms to solve business problems.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 7 | Linear & Logistic Regression | Assumptions, R-squared, Log-odds, Multicollinearity | Build and interpret a linear model from scratch |
| 8 | Tree-Based Models | Decision Trees, Random Forests, XGBoost, Feature Importance | Train an XGBoost model on a classification task |
| 9 | Unsupervised Learning | K-Means Clustering, PCA, Dimensionality Reduction | Segment a customer dataset using K-Means |
| 10 | Evaluation Metrics | Precision, Recall, ROC-AUC, F1-Score, RMSE | Write a custom metric evaluation script |

### Weeks 11-12: Product Sense & Behavioral
Translating data into business value.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 11 | Product Case Studies | Metric definition, funnel analysis, identifying root causes | Conduct 3 Product Sense mock interviews |
| 12 | Behavioral & Polish | Communicating complex concepts to non-technical stakeholders | Draft 5 STAR stories focusing on impact and stakeholder management |

## Milestones & Checkpoints

- [ ] **End of Week 3:** Can write a complex SQL query with Window functions without using Google.
- [ ] **End of Week 6:** Can confidently explain the math behind an A/B test and explain what a p-value is to a layperson.
- [ ] **End of Week 10:** Can articulate the trade-off between Random Forests and Logistic Regression for a given problem.
- [ ] **End of Week 11:** Mastered the framework for tackling open-ended Product/Business Case questions.

## Company Recommendations

- **Product-Analytics Focused (Meta, Airbnb):** Heavy emphasis on SQL, A/B Testing, and Product Sense. Less focus on deep ML algorithms.
- **Algorithm/Modeling Focused (Uber, Netflix):** Heavy emphasis on ML theory, recommendation systems, forecasting, and coding.
- **Fintech (Capital One, Stripe):** Focus on risk modeling, logistic regression, interpretability, and rigorous statistics.

## Interview Readiness Checklist

- [ ] Flawless execution of Window Functions in SQL.
- [ ] Clear understanding of how to detect and handle biased data.
- [ ] Can define success metrics for an abstract product (e.g., "Define success metrics for Instagram Stories").
- [ ] Strong STAR stories showcasing times your analysis led directly to a business decision.
