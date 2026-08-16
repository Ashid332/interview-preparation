# Model Evaluation

## Overview
Building a model is only half the battle; knowing how to evaluate it is critical. This topic covers classification metrics (Precision, Recall, F1-Score, ROC-AUC) and regression metrics (RMSE, MAE, R-squared), as well as understanding when to use which metric based on business context and class imbalance.

## Interview Questions

### Q1: When would you use ROC-AUC over Precision-Recall AUC?
**Difficulty:** Medium-Hard | **Frequency:** High | **Companies:** Meta, LinkedIn, Stripe

**Excellent Answer:**
ROC-AUC evaluates how well a model distinguishes between classes across all threshold values, plotting True Positive Rate vs. False Positive Rate. It is symmetric and treats both classes equally.
PR-AUC plots Precision vs. Recall. It is highly sensitive to class imbalance and focuses specifically on the positive class.
I would use PR-AUC when dealing with highly imbalanced datasets where the positive class is rare and more important (e.g., fraud detection). ROC-AUC can be overly optimistic in imbalanced scenarios because a large number of True Negatives can keep the False Positive Rate low even if the model is performing poorly on the minority class.

**Common Mistakes:**
- Stating that ROC-AUC is always the best metric for classification.
- Failing to explain the mathematical reason why ROC-AUC struggles with severe imbalance.

## Real-World Applications
- Using Recall as the primary metric for cancer screening models (false negatives are deadly).
- Using Precision for YouTube video recommendations (false positives cause user annoyance).

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Metric Calculation | Given a confusion matrix, calculate Precision, Recall, F1 | Easy | None |
| Imbalanced Data | Optimize a classifier on a 99:1 imbalanced dataset | Medium | None |

## Hiring Manager Perspective
Candidates often default to Accuracy, which is a massive red flag if the data is imbalanced. I look for a candidate who ties the evaluation metric directly to the business problem. A good engineer knows that metrics are proxies for business goals.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Generate 5 scenarios with different business goals and ask me to select the most appropriate evaluation metric for each."
- "Explain the mathematical difference between ROC-AUC and PR-AUC with a numerical example."
