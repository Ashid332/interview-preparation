# Machine Learning Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| Supervised Learning | Training a model on labeled data (mapping inputs to known outputs). |
| Unsupervised Learning | Finding patterns in unlabeled data (clustering, dimensionality reduction). |
| Overfitting | When a model learns the training data too well, capturing noise and failing to generalize. |
| Bias-Variance Tradeoff | High Bias = Underfitting. High Variance = Overfitting. You seek the sweet spot. |

## Must-Know Items
- Evaluation metrics: Accuracy, Precision, Recall, F1-Score, ROC-AUC for classification; RMSE, MAE for regression.
- Cross-validation (k-fold).
- Regularization techniques (L1/Lasso, L2/Ridge, Dropout) to prevent overfitting.
- Gradient Descent optimization.

## Common Interview Questions (Quick)
1. Explain the Bias-Variance tradeoff.
2. What is the difference between Precision and Recall? When would you prioritize one over the other?
3. How do you handle imbalanced datasets?
4. Explain how a Random Forest works.

## Critical Commands/Patterns
*Standard Sklearn Workflow:*
```python
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

model = RandomForestClassifier()
model.fit(X_train, y_train)

predictions = model.predict(X_test)
print(classification_report(y_test, predictions))
```

## Decision Framework
- **Algorithm Selection:**
  - Tabular data -> Tree-based models (XGBoost, Random Forest).
  - Images/Audio -> CNNs.
  - Sequential/Text data -> Transformers, RNNs.
- **Imbalanced Data:** Use SMOTE (oversampling), undersampling, or adjust class weights rather than relying solely on accuracy.

## Common Mistakes
- Data leakage: Using information from the test set during training (e.g., scaling data *before* splitting).
- Ignoring data distribution and assuming standard normal without verification.
- Focusing only on Accuracy when classes are highly imbalanced (e.g., fraud detection).

## One-Minute Review
- ML is about generalization. Understand the end-to-end pipeline: Data Cleaning -> Feature Engineering -> Model Selection -> Training -> Evaluation -> Deployment. Master your evaluation metrics.
