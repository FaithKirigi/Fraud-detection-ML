# 🕵️‍♀️ Fraud Detection in Financial Transactions

## 📖 Overview  
This project uses machine learning to detect fraudulent financial transactions based on behavior patterns, transaction time, user demographics, and geolocation. It applies multiple classification algorithms and compares their effectiveness on an imbalanced dataset.

---

## 🎯 Objectives  
- Identify fraudulent transactions from a large dataset  
- Perform feature engineering to enhance model performance  
- Handle class imbalance and evaluate model metrics beyond accuracy  

---

## 📊 Dataset  
- **Source**: [Kaggle - Synthetic Financial Dataset For Fraud Detection](https://www.kaggle.com/datasets/kartik2112/fraud-detection)  
- **Records**: ~1.3 million  
- **Fraudulent Transactions**: ~0.57%  
- **Key Features**: `amt`, `dob`, `lat/long`, `trans_date_trans_time`, `merchant`, etc.

---

## 🧰 Tools & Technologies  
- **Language**: Python  
- **Notebook**: Google Colab  
- **Libraries**: pandas, numpy, seaborn, matplotlib, scikit-learn, geopy

---

## 🛠️ Feature Engineering  
- Extracted **age** from `dob`  
- Derived `transaction_hour`, `day`, and `day_name` from timestamp  
- Calculated geolocation **distance** between user and merchant using `geopy`  
- Created binary label `is_fraud` for classification  

---

## 🔍 Exploratory Data Analysis  
- Distribution of transaction amounts and locations  
- Class imbalance visualization  
- Feature importance exploration  

---

## 🤖 Models Trained  
- Logistic Regression  
- SGD Classifier  
- K-Nearest Neighbors  
- Decision Tree Classifier  
- Support Vector Machine  

---

## 🧪 Evaluation Metrics  
- **Confusion Matrix**  
- **Classification Report** (Precision, Recall, F1-Score)  
- Special focus on improving **Recall**, to better catch fraudulent activity

---

