## 🌴 Holiday Package Purchase Prediction Using Machine Learning

## 📌 Project Overview
"Trips & Travel.Com" wants to expand its customer base by launching a new **Wellness Tourism Package**. Previously, random customer outreach led to high marketing costs with only an 18% conversion rate. This project builds a Machine Learning classification model to predict which customers are most likely to purchase the new package, helping the company optimize its marketing expenditure.

## 🎯 Project Objectives
- Clean and preprocess customer demographic and interaction data.
- Perform feature engineering to extract meaningful attributes (`TotalVisiting`).
- Train and compare multiple classification algorithms (Logistic Regression, Decision Tree, Random Forest, Gradient Boosting).
- Optimize the best-performing model using Hyperparameter Tuning (`RandomizedSearchCV`).
- Evaluate model performance using Accuracy, Precision, Recall, F1-Score, and ROC-AUC Curve.

## 🛠️ Technologies & Libraries Used
- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Plotly
- Scikit-Learn
- Jupyter Notebook

## 📂 Dataset Information
The dataset (`Travel.csv`) is sourced from Kaggle and contains **4,888 records** and **20 columns**:
- **Target Variable:** `ProdTaken` (0 = No, 1 = Yes)
- **Customer Details:** `CustomerID`, `Age`, `Gender`, `MaritalStatus`, `Occupation`, `Designation`, `MonthlyIncome`, `Passport`, `OwnCar`, `CityTier`
- **Interaction & Travel Details:** `TypeofContact`, `DurationOfPitch`, `NumberOfPersonVisiting`, `NumberOfFollowups`, `ProductPitched`, `PreferredPropertyStar`, `NumberOfTrips`, `PitchSatisfactionScore`, `NumberOfChildrenVisiting`

## 🧹 Data Cleaning & Feature Engineering
- **Missing Value Imputation:** Filled numerical missing values (`Age`, `DurationOfPitch`, `NumberOfTrips`, `MonthlyIncome`) with the **median**, and categorical/discrete missing values (`TypeofContact`, `NumberOfFollowups`, `PreferredPropertyStar`, `NumberOfChildrenVisiting`) with the **mode**.
- **Data Standardization:** Corrected typo in `Gender` (`Fe Male` → `Female`) and merged `Single` into `Unmarried` under `MaritalStatus`.
- **Feature Extraction:** Created a new feature `TotalVisiting` by combining `NumberOfPersonVisiting` and `NumberOfChildrenVisiting`, and dropped redundant columns (`CustomerID`, individual visiting counts).
- **Encoding & Scaling:** Applied `OneHotEncoder` for categorical features and `StandardScaler` for numerical features using `ColumnTransformer`.

## 🤖 Model Training & Evaluation
Four classification models were trained and evaluated on an 80-20 train-test split:

| Model | Test Accuracy | Test F1-Score | Test Precision | Test Recall | ROC-AUC Score |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Logistic Regression | 83.64% | 0.8087 | 0.6914 | 0.2932 | 0.6307 |
| Decision Tree | 91.51% | 0.9144 | 0.7967 | 0.7592 | 0.8561 |
| Random Forest (Base) | 92.33% | 0.9170 | 0.9603 | 0.6335 | 0.8136 |
| Gradient Boosting | 85.89% | 0.8398 | 0.7732 | 0.3927 | 0.6824 |

### 🔧 Hyperparameter Tuning
- Tuned the **Random Forest Classifier** using `RandomizedSearchCV` (`n_estimators=1000`, `max_features=7`, `min_samples_split=2`, `max_depth=None`).
- **Final Tuned Model Performance (Test Set):**
  - **Accuracy:** 93.05%
  - **F1-Score:** 0.9255
  - **Precision:** 0.9624
  - **Recall:** 0.6702
  - **ROC-AUC Score:** 0.8319

## 📈 Data Visualizations
- **ROC-AUC Curve:** Plotted the Receiver Operating Characteristic curve (`auc.png`) for the tuned Random Forest Classifier to visualize the trade-off between sensitivity and specificity.

## ⚙️ How to Run This Project
1. Install Python and Jupyter Notebook.
2. Install the required libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn plotly scikit-learn

## 📁 Project Structure

Plaintext
Holiday-Package-Prediction/
│
├── Holiday_Package_Prediction.ipynb
├── Travel.csv
├── auc.png
└── README.md

Email:sakshikachare444@gmail.com

GitHub: https://github.com/Sakshi-Kachare

\---

⭐ This project demonstrates end-to-end Machine Learning workflow including Data Cleaning, Feature Engineering, Model Comparison, and Hyperparameter Tuning.
