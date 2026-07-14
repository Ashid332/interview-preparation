# Feature Engineering

## Overview
Feature engineering is the process of using domain knowledge to extract features from raw data via data mining techniques. It includes imputation, encoding categorical variables, scaling, normalization, and creating interaction terms. Interviewers want to see how you handle messy, real-world data.

## Interview Questions

### Q1: How do you handle missing data in a dataset?
**Difficulty:** Easy-Medium | **Frequency:** Very High | **Companies:** Airbnb, Lyft, Pinterest

**Excellent Answer:**
The approach depends on the mechanism of missingness (MCAR, MAR, MNAR). 
1. **Deletion:** If missing data is completely random (MCAR) and a very small percentage, row deletion might be acceptable.
2. **Simple Imputation:** Using mean/median for numerical or mode for categorical. This is fast but reduces variance and can introduce bias.
3. **Advanced Imputation:** Using models like KNN or iterative imputation (e.g., MICE) to predict missing values based on other features.
4. **Feature Encoding:** Creating a boolean flag `is_missing` so the model can learn if the absence of data itself is predictive (common in MNAR scenarios).
I usually start with simple imputation plus a missing indicator, then test if advanced imputation improves cross-validation metrics.

**Common Mistakes:**
- Blindly filling all missing numerical values with 0.
- Dropping columns with missing data without checking if the missingness correlates with the target.

## Real-World Applications
- Handling missing sensor data in IoT devices due to network drops.
- Dealing with optional fields in user registration forms.

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Categorical Encoding | Compare One-Hot, Target, and Frequency encoding | Medium | [Link](#) |
| Time Series Features | Create lag and rolling window features for sales data | Medium | [Link](#) |

## Hiring Manager Perspective
Real data is garbage. I need to know the candidate can clean it up effectively. The ability to create a clever new feature from existing data often yields a higher performance boost than spending days tuning hyper-parameters on a neural network.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Give me a messy, hypothetical dataset description. Ask me to outline my end-to-end feature engineering pipeline."
- "What are the pros and cons of Target Encoding, and how do you prevent data leakage when using it?"
