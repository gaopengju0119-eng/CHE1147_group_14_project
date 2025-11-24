# CHE1147 Project: Heat Capacity Prediction using QM9 Dataset

**Group 14**
* **Members:** Matt Smrke, Pengju Gao, Sebastian Cook
* **Course:** CHE1147H, Chemical Data Science and Engineering

---

## 📌 Project Overview
We predicted the **Heat Capacity ($C_v$)** using the **QM9 dataset**.

**Key Highlights:**
* Result (outputs and figures) are shown in **CHE1147_Group14.ipynb**
* You can also open it on **Colab** (containing output and figures): https://colab.research.google.com/drive/1JpOU4Ce4eg8XFI477AFu9eXqG6d6VAQJ#scrollTo=EliGDh4MKQyE
* **Data:** QM9 dataset.
* **Methods:** kNN as baseline,  compared Ridge, XGBoost, Random Forest.
* **Feature selection:** from 21 to 10 features.
* **Hyperparameter tuning:** Ridge, XGBoost and Random Forest.
* **Best Model:** Tuned XGBoost Regressor on 10 selected features, with R2 (0.97) and MAE (0.52 cal/mol·K), and high efficiency.
* **Interpretability:** SHAP analysis.
* **Reliability:** Uncertainty estimation using Bootstrap Ensembles.

---

## 🚀 How to Run the Code
0. **Conda is necessary**
1. **Create the environment (on terminal):** conda env create -f environment.yml
2. **Activate the environment (on terminal):** conda activate che1147_group_14
3. **Set Python Interpreter to 'che1147_group_14'**
4. **Run the script:** python CHE1147_Group14.py

---

## 📊 Key Results & Performance Comparison

| Model Name           | Feature Count                             | $R^2$ Score | MAE (cal/mol·K) | Status & Evaluation                                                             |
|:---------------------|:------------------------------------------|:------------|:----------------|:--------------------------------------------------------------------------------|
| **kNN (Baseline)**   | 14 (Lasso Selected)                       | 0.93        | 0.76            | ⚠️ **Benchmark**: Effective.                                                    |
| **Ridge Regression** | 21 (All Features)                         | -308.46     | 0.97            | ❌ **Failed**: Proves the relationship is highly non-linear.                     |
| **Random Forest**    | 10 (Optimized & hyperparameter tuned)     | 0.98        | 0.47            | 🥈 **High performance and cost**: Excessive computational time and high memory. |
| **XGBoost**          | **10 (Optimized & hyperparameter tuned)** | **0.97**    | **0.52**        | 🏆 **CHAMPION**: Highest accuracy with lowest data requirement.                 |

---

## 📂 Repository Key Structure
```text
├── README.md
├── environment.yml
├── champion_model_XGBoost.joblib
├── CHE1147_Group14.ipynb
└── CHE1147_Group14.py