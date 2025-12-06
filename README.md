# 🎓 Student Academic Risk Prediction (Early Warning System)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit--Learn%20%7C%20Pandas-orange)
![Deployment](https://img.shields.io/badge/Deployment-Gradio-green)

## 📋 Project Overview
This project is a Data Science initiative designed to build an **Early Warning System (EWS)** for higher education institutions. By analyzing historical academic data (SGPA and CGPA), the system predicts whether a student is in a **"Safe"** zone or **"At Risk"** of failing/dropping out.

The goal is to assist academic counselors in identifying struggling students early, allowing for timely intervention before the final exams.

## 🚀 Features
- **Data Analysis:** automatic cleaning and preprocessing of student exam results.
- **Machine Learning Model:** Uses **Random Forest Classifier** for high-accuracy prediction.
- **Risk Classification:**
  - 🟢 **Safe:** Predicted to Pass.
  - 🔴 **At Risk:** Predicted to Fail or Pass with Grace.
- **Web Interface:** Interactive dashboard using **Gradio** for real-time predictions.

## 📂 Dataset
The project uses the **College Exam Result Dataset 2025**.
- **Source:** University Academic Records (B.Tech Program).
- **Key Features used for Modeling:**
  1. **SGPA** (Semester Grade Point Average)
  2. **CGPA** (Cumulative Grade Point Average)
- **Target Variable:** Derived from `Result Description` (PASS vs FAIL/GRACE).

## 🛠️ Tech Stack
* **Language:** Python
* **Data Processing:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (Random Forest)
* **Deployment/UI:** Gradio

## 📊 Project Workflow (CRISP-DM)
1.  **Business Understanding:** Identifying the need to reduce dropout rates.
2.  **Data Understanding:** Analyzing the correlation between SGPA/CGPA and failure rates.
3.  **Data Preparation:** * Handling missing values.
    * Label Encoding (`PASS` -> 0, `FAIL/GRACE` -> 1).
4.  **Modeling:** Training a Random Forest Classifier with 50 estimators.
5.  **Evaluation:** Achieving high accuracy with low false negatives (high recall for risk detection).
6.  **Deployment:** Creating a user-friendly web app.

## 💻 How to Run This Project

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/student-risk-prediction.git](https://github.com/your-username/student-risk-prediction.git)
cd student-risk-prediction
