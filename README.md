# Credit Card Fraud Detection — Model Evaluation & Risk Controls

## Professional focus
An imbalanced-classification project relevant to transaction monitoring and operational financial-crime risk. The emphasis is on leakage-safe model development and metrics that reflect the cost of missed fraud and false alerts.

## Business questions
- How effectively can fraudulent transactions be identified when fraud is rare?
- What trade-off exists between fraud capture (recall) and investigation workload (precision)?
- Does resampling improve minority-class detection on unseen data?
- Which model and alert threshold best support a defined operational capacity?

## Existing notebooks
- `Credit Card Fraud Detection.ipynb`
- `Model_Final.ipynb`

## Evaluation principles and improvement plan
1. Split data into train and test sets before fitting scalers, encoders or resampling methods.
2. Use stratified splits where appropriate.
3. Put preprocessing and SMOTE inside an imbalanced-learn pipeline so resampling occurs only within each training fold during cross-validation.
4. Compare a simple baseline with logistic regression and tree-based models.
5. Report fraud-class precision, recall, F1, confusion matrix, ROC-AUC and especially PR-AUC; do not rely on accuracy alone.
6. Calculate ROC-AUC from continuous scores such as `predict_proba` or `decision_function`, not hard class predictions.
7. Select an operating threshold using business costs and investigation capacity, not only a default 0.50 threshold.
8. Check results on an untouched test set and document limitations.

## Tools
Python, pandas, NumPy, scikit-learn, imbalanced-learn, Matplotlib/Seaborn.

## Important interpretation
A high overall accuracy can be misleading in a highly imbalanced fraud dataset. Model performance must be judged on the fraud class and the cost of false negatives and false positives. SMOTE is a training technique, not a way to alter the real-world test distribution.

## Disclaimer
Educational analysis only. It is not a live fraud monitoring system and should not be used to make real transaction decisions.
