# PRODIGY_DS_TASK3
Decision Tree Classifier – Customer Purchase Prediction
Objective
Predict whether a customer will purchase a product/service based on their demographic and behavioral attributes.
Dataset Overview
Total Records: 4,119
Features: 17 input features (e.g., age, job, marital status, education, housing loan, contact type, month, day_of_week, duration, campaign, pdays, previous, poutcome, consumer price index, consumer confidence index).
Target Variable: deposit (0 = No Purchase, 1 = Purchase)
Class Distribution:
No Purchase: 3,668
Purchase: 451 (Imbalanced dataset)
Model 1 – Gini Criterion
Hyperparameters: max_depth=5, min_samples_split=10
Training Accuracy: 91.48%
Testing Accuracy: 89.90
Confusion Matrix:
[[905  25]
 [ 79  21]
Classification Report:
Class 0 (No Purchase): Precision = 0.92, Recall = 0.97, F1 = 0.95
Class 1 (Purchase): Precision = 0.46, Recall = 0.21, F1 = 0.29
Overall Accuracy: 90%
Model 2 – Entropy Criterion
Hyperparameters: max_depth=4, min_samples_split=15
Training Accuracy: 90.80%
Testing Accuracy: 90.48%
Confusion Matrix:
[[915  15]
 [ 83  17]]
Classification Report:
Class 0 (No Purchase): Precision = 0.92, Recall = 0.98, F1 = 0.95
Class 1 (Purchase): Precision = 0.53, Recall = 0.17, F1 = 0.26
Overall Accuracy: 90%
Insights
The model performs well in predicting non-purchasers (Class 0) but struggles with correctly identifying purchasers (Class 1) due to class imbalance.
Both Gini and Entropy-based decision trees show similar accuracy (~90%).
Recall for purchasers is low, meaning many actual purchasers are being missed.
Features like duration, contact method, month, and poutcome are likely to be key decision factors (based on decision tree splits).
Recommendations
Handle Class Imbalance
Use oversampling (SMOTE) or undersampling to balance classes.
Try class weight adjustments in the Decision Tree.
Feature Engineering
Extract interaction features (e.g., campaign * previous contacts).
Convert categorical variables into meaningful numeric encodings
Model Improvements
Experiment with Random Forest or Gradient Boosting for better recall.
Tune hyperparameters with GridSearchCV.
