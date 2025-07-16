# 💳 Credit Risk Prediction Using Machine Learning

This project focuses on building a machine learning model to predict the **credit risk level (`risk_rating`)** of loan applicants based on their financial and demographic attributes. 

📥 The dataset was obtained from an open-source educational platform, DQLab: https://storage.googleapis.com/dqlab-dataset/credit_scoring_dqlab.xlsx, as part of a data science learning module.


---

## 📘 Dataset Description

The dataset contains 900 loan application records from a financial institution, with the following features:

| Feature                   | Description                                                        |
|---------------------------|--------------------------------------------------------------------|
| `kode_kontrak`            | Unique contract ID *(not used in modeling)*                        |
| `pendapatan_setahun_juta`| Annual income in millions *(dropped due to low correlation)*       |
| `kpr_aktif`               | Whether the applicant has an active mortgage ("YA"/"TIDAK")       |
| `durasi_pinjaman_bulan`  | Loan duration in months *(dropped due to low correlation)*         |
| `jumlah_tanggungan`       | Number of dependents                                               |
| `rata_rata_overdue`       | Average overdue time (e.g., "0 - 30 days", converted to ordinal)   |
| `risk_rating`             | Target variable: 1 (low risk) to 4 (high risk)                     |

✅ **No missing values** were found in the dataset.

---

## 🎯 Objective

To build classification models that can predict the `risk_rating` of applicants using selected features.

---

## 🔍 Exploratory Data Analysis (EDA)

- Converted `kpr_aktif` from categorical to binary (YA = 1, TIDAK = 0)
- Mapped `rata_rata_overdue` categories to ordinal numeric scale
- Dropped `kode_kontrak`, `pendapatan_setahun_juta`, and `durasi_pinjaman_bulan` due to low predictive value
- Dataset was clean (no nulls or duplicates)

📌 **Correlation Analysis**:
- `rata_rata_overdue` showed **very strong correlation** with `risk_rating` (~0.98)
- `jumlah_tanggungan` and `kpr_aktif` showed moderate correlation

---

## 🤖 Models Trained

Four machine learning algorithms were implemented and evaluated:

| Model                  | Accuracy | Observation                                                  |
|------------------------|----------|--------------------------------------------------------------|
| **Naive Bayes**        | 1.00     | Perfect accuracy, likely due to dominant features            |
| **K-Nearest Neighbors**| 1.00     | Identical performance; dataset is cleanly separable          |
| **Support Vector Machine** | 1.00 | Also achieved perfect accuracy                               |
| **Logistic Regression**| 0.8722   | More realistic performance; class 4 often misclassified      |

---

## 💡 Key Insights

- `rata_rata_overdue` is a highly predictive feature and may dominate classification
- Most models achieved perfect accuracy — indicating possible **overfitting** or **data leakage**
- Logistic Regression provided more realistic and generalizable results

---

## 📌 Suggestions for Future Work

- ✅ Apply **cross-validation** (e.g., K-Fold) to all models to assess generalization
- 🔁 Test models on **new or external datasets** to check real-world performance
- 🧪 Engineer additional features, e.g., `tanggungan/penghasilan` ratio
- 📊 Visualize decision boundaries or feature importance per model
- 🧠 Explore ensemble and explainable models (e.g., Random Forest, SHAP, LIME)

---

## 🧰 Tools Used

- Python 
- `pandas`, `matplotlib`, `seaborn`
- `scikit-learn`
- Google Colab (Jupyter Notebook)

---

## 📫 Contact

Feel free to reach out if you’d like to provide feedback, ask questions, or collaborate on similar machine learning projects!
📧 helenpatricia061006@gmail.com 🔗 www.linkedin.com/in/helenptrcia
