
# 💳 Fraud Detection with Machine Learning

## 📌 Overview

This project builds a **machine learning pipeline** to detect fraudulent credit card transactions. Using a large-scale synthetic dataset (\~1.8M transactions across 1,000 customers and 800 merchants), the goal is to accurately detect fraud while minimizing the financial impact of missed detections and false alarms.

---

## 🚀 Features

* **Data Preprocessing & Feature Engineering**

  * Cleaned and normalized transaction records
  * Engineered features: transaction time patterns, geographic distance, transaction amount bins
  * Salary enrichment using **Bureau of Labor Statistics (BLS) API**
  * Balanced dataset using **SMOTE & undersampling**

* **Machine Learning Models**

  * Logistic Regression
  * Random Forest
  * XGBoost (best-performing, AUC = **0.996**)

* **Cost-Sensitive Evaluation**

  * Traditional metrics: precision, recall, F1-score, AUC
  * Business-aware evaluation:

    * Missed fraud = **\$3,000 loss each**
    * Card reissue = **\$50 cost each**
    * False reissue churn = **0.5% cancellation × \$3,000**
  * Optimized threshold reduced projected losses from **\$1.82M → \$1.21M**

* **Fraud Insights**

  * Fraudulent transactions peak at **night (9 PM – 3 AM)**
  * **Low-value (< \$50)** transactions most fraud-prone
  * Categories like **online shopping** and **groceries** had highest fraud rates
  * Fraud clusters in **densely populated metro regions**

---

## 📂 Dataset

* **Source**: Synthetic dataset (Sparkov Data Generator)
* **Records**: \~1.85M transactions (2019–2020)
* **Attributes**: Customer demographics, merchant details, transaction time/amount/location, fraud labels
* Publicly available on Kaggle: *Credit Card Fraud Detection Dataset*

---

## 📊 Results

| Model               | AUC       | Recall | Precision | F1-score |
| ------------------- | --------- | ------ | --------- | -------- |
| Logistic Regression | 0.50      | Low    | Low       | Poor     |
| Random Forest       | 0.975     | High   | Balanced  | Strong   |
| **XGBoost**         | **0.996** | High   | Balanced  | **Best** |

* **Cost optimization** showed **XGBoost with threshold tuning** provided the lowest financial loss.

---

## 🛠️ Tech Stack

* **Languages**: Python
* **Libraries**: Pandas, NumPy, Scikit-learn, XGBoost, Imbalanced-learn, Matplotlib, Seaborn
* **Environment**: Jupyter Notebook / Python 3.12


## 📌 Future Work

* Deploy fraud detection as a **Flask/Streamlit web app**
* Incorporate **real-time streaming (Kafka, Spark)**
* Expand to multi-source datasets (bank logs, customer profiles)
* Integrate **explainable AI (SHAP, LIME)** for interpretability

---

## 👨‍💻 Author

**Raja Shaker Chinthakindi**
Master’s in Applied Data Science @ University of Southern California (USC)
