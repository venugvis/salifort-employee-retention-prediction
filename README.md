# Salifort Motors Employee Retention Prediction

## Project Overview

This project focuses on predicting employee attrition at Salifort Motors, a fictional multinational alternative energy vehicle manufacturer. The primary objective is to identify key drivers of employee turnover and develop a predictive model to assist HR in making data-informed retention decisions.

The work was completed as part of the Google Advanced Data Analytics Professional Certificate and refined to meet professional portfolio standards.

---

## Dataset

The dataset contains 14,999 anonymized employee records with the following features:

- Satisfaction level
- Last evaluation score
- Number of projects
- Average monthly hours
- Time spent at the company
- Work accident history
- Whether the employee left the company (target)
- Recent promotion status
- Department
- Salary level (low, medium, high)

All data is structured, clean, and self-reported.

---

## Key Insights

Exploratory data analysis revealed:

- High and low extremes in average monthly hours are both associated with higher attrition.
- Longer tenure and lack of promotions correlate with higher turnover rates.
- Low salary groups and certain departments (e.g., sales, technical, support) show elevated attrition.
- Satisfaction level is a strong inverse predictor of attrition.

---

## Modeling Approach

Several models were developed and evaluated:

1. **Baseline Logistic Regression**  
2. **Tuned Logistic Regression using GridSearchCV**  
3. **Baseline Random Forest Classifier**  
4. **Tuned Random Forest Classifier using GridSearchCV**

---

### Model Comparison

| Model                       | Accuracy | Recall (Attrition Class) | Precision (Attrition Class) | F1-Score (Attrition Class) |
|----------------------------|----------|---------------------------|------------------------------|-----------------------------|
| Baseline Logistic Regression | 0.75     | 0.05                      | 0.34                         | 0.08                        |
| Tuned Logistic Regression    | 0.61     | 0.68                      | 0.34                         | 0.46                        |
| Baseline Random Forest       | 0.97     | 0.94                      | 0.93                         | 0.94                        |
| Tuned Random Forest (Final)  | 0.97     | 0.96                      | 0.90                         | 0.93                        |

---

**Final Model Chosen**: Tuned Random Forest  
This model offered the best balance of **high recall** (to catch at-risk employees), **strong precision**, and overall stability. It also maintained 97% accuracy while outperforming simpler models on class imbalance and feature interaction handling.

The Random Forest model was selected as the final model due to its superior performance:

- Accuracy: 97%
- Recall (attrition class): 96%
- F1-Score (attrition class): 93%

The model was saved using `joblib` and can be reused without retraining.

---

## Feature Importance

The top predictors of employee attrition were:

- Time spent at the company
- Average monthly hours
- Number of projects
- Work accident history
- Low salary level

These insights support HR’s ability to target interventions with high precision and reduce avoidable turnover.

---

## Business Recommendations

Based on the findings:

- Monitor employees with long tenure and extreme workloads more closely.
- Review promotion policies and identify potential gaps in career progression.
- Evaluate department-level retention strategies, particularly for roles with high attrition.
- Reassess salary structures where applicable, especially in high-risk segments.

---

## Next Steps

- Integrate this model into an HR analytics dashboard or alert system.
- Apply SHAP or LIME to improve model explainability at the individual level.
- Explore time-based patterns in attrition or combine with engagement survey data.
