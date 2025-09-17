# Fraudulent Job Detection

## 📌 Project Overview
This project aims to detect fraudulent job postings using **Exploratory Data Analysis (EDA)** and **Machine Learning** techniques. Online job postings often contain misleading or fraudulent information, and this system helps classify whether a job is **fraudulent (1)** or **legitimate (0)**.

The dataset is highly imbalanced, with far more legitimate jobs compared to fraudulent ones, as shown below:

![Fraud vs Non-Fraud Count](ce2972ed-34ae-4626-b4da-cb1b6d9102a3.png)

---

## 🔍 Approach
1. **Data Cleaning & EDA**
   - Handled **null values** and missing fields.
   - Identified **empty or suspicious information**.
   - Explored class imbalance in fraudulent vs non-fraudulent jobs.

2. **Text Preprocessing & Feature Engineering**
   - Applied **Natural Language Processing (NLP)** techniques.
   - **Tokenization** of job descriptions.
   - **Vectorization** using Bag-of-Words / TF-IDF.

3. **Model Training**
   - Trained four machine learning models:
     - Logistic Regression
     - Multinomial Naïve Bayes
     - Support Vector Classifier (SVC)
     - XGBoost Classifier

---

## 📊 Results

### Model Performance Summary

| Model                  | Accuracy | Precision (Macro Avg) | Recall (Macro Avg) | F1-score (Macro Avg) |
|-------------------------|----------|------------------------|---------------------|-----------------------|
| Logistic Regression     | 0.89     | 0.90                   | 0.89                | 0.89                  |
| Multinomial Naïve Bayes | 0.83     | 0.84                   | 0.83                | 0.83                  |
| Support Vector Classifier (SVC) | 0.91 | 0.92               | 0.91                | 0.91                  |
| XGBoost Classifier      | 0.92     | 0.93                   | 0.92                | 0.92                  |

---

### Logistic Regression
- **Accuracy:** 0.89  
- Strong at catching legitimate jobs (recall = 0.98).  
- Slightly weaker on fraudulent jobs (recall = 0.81).  

| Class | Precision | Recall | F1-score | Support |
|-------|-----------|--------|----------|---------|
| Legitimate (0) | 0.81 | 0.98 | 0.89 | 161 |
| Fraudulent (1) | 0.98 | 0.81 | 0.88 | 186 |

---

### Multinomial Naïve Bayes
- **Accuracy:** 0.83  
- Performs well on legitimate jobs but weaker on fraudulent recall (0.72).  

| Class | Precision | Recall | F1-score | Support |
|-------|-----------|--------|----------|---------|
| Legitimate (0) | 0.76 | 0.94 | 0.84 | 167 |
| Fraudulent (1) | 0.93 | 0.72 | 0.81 | 180 |

---

### Support Vector Classifier (SVC)
- **Accuracy:** 0.91  
- Strong balance between fraud and non-fraud detection.  

| Class | Precision | Recall | F1-score | Support |
|-------|-----------|--------|----------|---------|
| Legitimate (0) | 0.87 | 0.97 | 0.92 | 175 |
| Fraudulent (1) | 0.97 | 0.85 | 0.90 | 172 |

---

### XGBoost Classifier
- **Accuracy:** 0.92 (Best overall)  
- Excellent at both fraud and non-fraud detection with balanced precision & recall.  

| Class | Precision | Recall | F1-score | Support |
|-------|-----------|--------|----------|---------|
| Legitimate (0) | 0.86 | 0.99 | 0.92 | 167 |
| Fraudulent (1) | 0.99 | 0.86 | 0.92 | 180 |

---

## ✅ Conclusion
- **XGBoost and SVC** achieved the best performance, with **92% and 91% accuracy** respectively.  
- **Logistic Regression** was reliable and interpretable, but slightly weaker on fraudulent recall.  
- **Multinomial Naïve Bayes** had the lowest performance, struggling to balance fraud detection.  

Overall, **XGBoost is the recommended model** for production deployment due to its high precision, recall, and balanced classification.

---
