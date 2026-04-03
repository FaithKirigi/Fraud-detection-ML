# Fraud Detection in Financial Transactions Using Machine Learning

## 1. Introduction

Fraudulent financial transactions pose a significant risk to both financial institutions and customers. As digital transactions continue to grow, so does the sophistication of fraud techniques.  

This project focuses on building a machine learning model capable of detecting fraudulent transactions with high accuracy while maintaining interpretability.

The goal is not just to build a model, but to understand the patterns behind fraudulent behavior and translate those insights into actionable insights.

---

## 2. Objectives

The key objectives of this project were:

- Demonstrate practical Python and data science skills  
- Perform in-depth exploratory data analysis (EDA)  
- Identify patterns associated with fraudulent transactions  
- Build and evaluate multiple machine learning models  
- Select and optimize the best-performing model  
- Derive meaningful insights for fraud prevention  

---

## 3. Dataset Description

The dataset used in this project was sourced from Kaggle and contains transactional financial data.

### Dataset Characteristics

- **Number of rows:** 1,296,675  
- **Number of columns:** 22  

### Data Types

- Float: 5  
- Integer: 5  
- Object (categorical): 12  

The dataset contained **no missing values**, eliminating the need for null-value imputation.

---

## 4. Data Preprocessing

Although the dataset was structurally clean, several transformations were required.

### 4.1 Feature Extraction

From the `trans_date_trans_time` column, the following features were extracted:

- Transaction hour  
- Day of the week  
- Month  

These features helped capture temporal fraud patterns.

### 4.2 Derived Features

- Created a new **age** feature from demographic data.

### 4.3 Initial Observations

- Presence of outliers in transaction amounts  
- Fraudulent transactions were extremely rare  

---

## 5. Exploratory Data Analysis (EDA)

EDA was used to uncover patterns and relationships in the data.

### 5.1 Transaction Distribution

- Female customers had a higher number of transactions  
- Transaction amounts contained significant outliers  

### 5.2 Fraud Patterns by Time

- Fraudulent transactions were **not evenly distributed**
- Peak fraud activity occurred between **7:00 PM and 4:00 AM**

### 5.3 Location Insights

- No significant difference in transaction distance between fraud and non-fraud  
- Location is **not a strong predictor** of fraud  

### 5.4 Category Insights

- Certain transaction categories showed higher fraud occurrence  
- Fraud cases were extremely few (< 5000)

### 5.5 Correlation Analysis

- **Transaction amount (`amt`)** showed the strongest correlation with fraud  

---

## 6. Feature Engineering

### 6.1 Outlier Handling

- Removed outliers to improve model performance  

### 6.2 Encoding Categorical Variables

Converted categorical features into numeric format:

- Gender  
- Job  
- Transaction category  

### 6.3 Multicollinearity Check

Removed redundant variables:

- `merch_long` and `long`  
- `merch_lat` and `lat`  
- `unix_time` (redundant)  
- `zip`  

Final dataset reduced to **8 key variables**

---

## 7. Handling Class Imbalance

Fraudulent transactions made up only **~0.5%** of the dataset.

### Approach Used

- **Undersampling** the majority class (non-fraud)

### Outcome

- Balanced dataset  
- Reduced bias toward non-fraud predictions  

---

## 8. Model Selection

The following models were evaluated:

- Logistic Regression  
- K-Nearest Neighbors (KNN)  
- Support Vector Classifier (SVC)  
- Decision Tree Classifier  

### Data Split

- **80%** training  
- **20%** testing  

---

## 9. Model Evaluation

### Performance Comparison

| Model                  | Accuracy |
|-----------------------|---------|
| Logistic Regression   | 0.84    |
| KNN                   | 0.91    |
| SVC                   | 0.62    |
| Decision Tree         | 0.97    |

The **Decision Tree Classifier** outperformed all other models.

---

## 10. Hyperparameter Tuning

### Decision Tree

- Controlled maximum depth  
- Set minimum samples per split  
- Prevented overfitting  

### Logistic Regression

- Strong regularization (`C = 0.01`)  
- L1 penalty for feature selection  

---

## 11. Confusion Matrix Analysis

### Decision Tree

- **True Positives:** 1387  
- **True Negatives:** 1435  
- **False Positives:** 73  
- **False Negatives:** 108  

### Logistic Regression

- **True Positives:** 1128  
- **True Negatives:** 1465  
- **False Positives:** 43  
- **False Negatives:** 367  

### Key Insight

- Decision Tree significantly reduced **false negatives**  
- Critical because missing fraud is more costly than false alerts  

---

## 12. Model Performance Insights

### Recall (Fraud Detection)

- Decision Tree: **93%**  
- Logistic Regression: **75%**  

### F1 Score

- Decision Tree: **94%**  
- Logistic Regression: **85%**  

The Decision Tree provides a better balance between precision and recall.

---

## 13. ROC Curve Analysis

- Decision Tree AUC: **0.98**  
- Logistic Regression AUC: **0.87**  

Decision Tree demonstrates superior classification performance.

---

## 14. Learning Curves

### Decision Tree

- High training score (~0.95)  
- Validation score improves with more data  
- Minimal gap → strong generalization  

### Logistic Regression

- Gradual improvement with more data  
- Initial overfitting reduced over time  

---

## 15. Feature Importance

Top predictors of fraud:

1. **Transaction Amount (`amt`)**  
2. Transaction category  
3. Transaction hour  

These align with real-world fraud detection practices.

---

## 16. Final Model Selection

The **Decision Tree Classifier** was selected because it:

- Achieved the highest accuracy  
- Had strong recall (critical for fraud detection)  
- Delivered high AUC  
- Maintained interpretability  

The model was retrained on the full dataset using optimized parameters.

---

## 17. Challenges Faced

### 17.1 Class Imbalance

- Fraud cases were extremely rare  
- Required resampling techniques  

### 17.2 Outliers

- Affected model performance  
- Required careful handling  

---

## 18. Recommendations for Improvement

- **Continuous Retraining**  
  - Update model with new data  

- **Enhance Dataset**  
  - Increase fraudulent transaction samples  

- **Advanced Models**  
  - Explore ensemble methods (Random Forest, XGBoost)  

- **Improved Imbalance Handling**  
  - Use SMOTE or similar techniques  

---

## 19. Business Impact

This project demonstrates how machine learning can:

- Detect fraud in real time  
- Reduce financial losses  
- Improve customer trust  

With the rise of digital transactions and fraud techniques, such systems are increasingly critical.

---

## 20. Conclusion

This project successfully developed a machine learning model capable of detecting fraudulent transactions with high accuracy.

### Key Takeaways

- Fraud detection requires handling imbalanced datasets carefully  
- Feature engineering significantly impacts performance  
- Decision Trees provide strong performance and interpretability  
- Transaction amount and timing are key fraud indicators  

The model provides a solid foundation for real-world fraud detection systems and future improvements.

---
