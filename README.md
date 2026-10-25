# Financial Distress Prediction Using Machine Learning

## Project Overview

This project develops a machine learning system to identify companies that may be at risk of financial distress or bankruptcy based on financial indicators.

It trains and evaluates Logistic Regression, Random Forest, and XGBoost classifiers. The models are compared using evaluation metrics, with particular attention to class imbalance in bankruptcy prediction. The goal is to build an early-warning tool that can support financial risk assessment and help analysts identify companies requiring further investigation.

## Objectives

- Predict potential corporate bankruptcy using financial indicators.
- Compare multiple machine learning classification algorithms.
- Address class imbalance and evaluate different classification thresholds.
- Evaluate performance using precision, recall, F1-score, ROC-AUC, and PR-AUC.
- Use SHAP explainability to understand the influence of financial features on predictions.

## Dataset

The project uses the **Taiwanese Bankruptcy Prediction dataset** from the UCI Machine Learning Repository. It contains approximately 6,819 company observations and 95 financial indicators, along with a target variable representing bankruptcy status.

**Note:** The dataset represents Taiwanese companies. Predictions for Indian companies or other markets require additional validation on relevant data.

## Machine Learning Models

### Logistic Regression
Used as a baseline classifier for bankruptcy prediction.

### Random Forest
Combines multiple decision trees to learn relationships between financial indicators and bankruptcy outcomes.

### XGBoost
Uses gradient-boosted decision trees to learn patterns in financial data. It was selected as the preferred model in the project's model-comparison experiments.

Hyperparameter tuning and cross-validation are used to evaluate model performance and support model selection.

## Methodology

1. **Data loading:** Import the dataset and inspect its structure.
2. **Exploratory data analysis:** Examine feature distributions, data quality, and target-class distribution.
3. **Preprocessing:** Prepare features and the target variable for modelling.
4. **Train-test split:** Separate training and held-out test data.
5. **Model training:** Train Logistic Regression, Random Forest, and XGBoost classifiers.
6. **Model evaluation:** Compare models using classification and ranking-based metrics.
7. **Threshold optimization:** Explore probability thresholds to balance precision and recall.
8. **Explainability:** Use SHAP to investigate feature contributions.
9. **Final evaluation:** Assess the selected model on held-out test data.

## Evaluation Metrics

| Metric | Purpose |
|---|---|
| Accuracy | Proportion of correct predictions |
| Precision | Proportion of predicted bankruptcy cases that are actual bankruptcy cases |
| Recall | Proportion of actual bankruptcy cases identified |
| F1-score | Harmonic balance between precision and recall |
| ROC-AUC | Measures how well the model ranks positive cases above negative cases |
| PR-AUC | Evaluates precision-recall performance, particularly useful for imbalanced data |
| Confusion Matrix | Shows true positives, true negatives, false positives, and false negatives |

Because bankruptcy cases are relatively uncommon, accuracy alone is insufficient to assess model quality. Precision and recall are particularly important for financial risk screening.

## Explainable AI with SHAP

The project uses SHAP (SHapley Additive exPlanations) to help interpret machine learning predictions. SHAP can help identify influential financial indicators, examine feature contributions to individual predictions, and improve model interpretability.

Feature contributions describe model behaviour; they do not prove that a particular indicator causes bankruptcy.

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- XGBoost
- SHAP
- Jupyter Notebook / Google Colab

## Results

In one intermediate experiment, the tuned XGBoost model achieved the following results for the bankruptcy class at a probability threshold of 0.5:

| Metric | Result |
|---|---:|
| Precision | 0.50 |
| Recall | 0.52 |
| F1-score | 0.51 |

These figures are from an intermediate experiment and should not be treated as the final model's results unless they match the final evaluation output. Report metrics from the selected model and held-out test set, including the threshold used.

## Potential Applications

- Preliminary corporate credit-risk screening
- Financial risk analysis
- Investment research support
- Corporate financial monitoring
- Identification of companies requiring further financial review

The model is intended to support human analysis rather than replace professional financial judgement.

## Limitations

- The dataset is based on Taiwanese companies and may not generalise to other economies.
- Historical data may not reflect future economic conditions.
- Class imbalance can affect precision and recall.
- Predictions depend on the quality and relevance of input financial indicators.
- Outputs are estimates, not definitive bankruptcy decisions.
- External validation is required before real-world deployment.

## Future Improvements

- Validate the model on financial data from Indian companies.
- Incorporate more recent financial statements and macroeconomic indicators.
- Evaluate additional models and probability calibration methods.
- Improve feature engineering using domain-specific financial ratios.
- Integrate the prediction pipeline into a financial analytics dashboard.
- Monitor model drift and performance over time.

## Disclaimer

This project is developed for educational and research purposes. It is not financial, investment, lending, or credit-rating advice. Predictions should be independently validated before being used in real-world decisions.

## Author

**Mayank Gupta**  
M.Sc. Data Science

GitHub: Add your GitHub profile URL
