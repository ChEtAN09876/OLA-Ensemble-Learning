# 🚗 Ola Driver Attrition Prediction

## 📌 Problem Statement

Ola is facing high churn rates among its drivers, which negatively impacts morale and increases acquisition costs. As a data scientist at Ola, your task is to build a machine learning model that predicts **whether a driver is likely to leave the company** based on their demographic, performance, and tenure-related attributes.

---

## 🧾 Dataset Description

- **File:** `ola_driver.csv`
- **Period Covered:** Monthly data for 2019 and 2020

### 📊 Columns:

| Column Name            | Description |
|------------------------|-------------|
| MMMM-YY                | Reporting date (monthly) |
| Driver_ID              | Unique identifier for each driver |
| Age                    | Age of the driver |
| Gender                 | 0: Male, 1: Female |
| City                   | Driver's city code |
| Education_Level        | 0: 10+, 1: 12+, 2: Graduate |
| Income                 | Monthly average income |
| Date Of Joining        | Date when driver joined |
| LastWorkingDate        | Last working day of the driver (if applicable) |
| Joining Designation    | Designation when joined |
| Grade                  | Grade at time of reporting |
| Total Business Value   | Business acquired in a month (negative = refund/cancellation) |
| Quarterly Rating       | Rating on a scale from 1 to 5 |

---

## 🔧 Steps Followed

### 1. 📊 Exploratory Data Analysis
- Structure & summary of dataset
- Conversion of date-like columns to datetime
- Identification of missing values
- Basic statistics and data distributions

### 2. 🧹 Data Cleaning & Preprocessing
- KNN imputation for missing numerical values
- Aggregation at the `Driver_ID` level
- Feature reduction to eliminate redundant monthly records

### 3. 🛠 Feature Engineering
- `quarterly_rating_increase`: 1 if driver’s rating improved, else 0
- `income_increase`: 1 if monthly income improved, else 0
- `target`: 1 if driver has a last working date (i.e., churned), else 0

### 4. 📈 Statistical & Correlation Analysis
- Pearson correlation heatmap
- Interactions between key variables

### 5. 🧠 Data Transformation
- One-hot encoding of categorical variables
- Train-test split
- Standardization using `StandardScaler`

---

## 🤖 Machine Learning Models

### ✅ Algorithms Used:
- **Bagging** (Random Forest)
- **Boosting** (XGBoost, Gradient Boosting)
- Compared models using:
  - Accuracy
  - ROC AUC
  - F1-score
  - Classification Report

### ⚙️ Hyperparameter Tuning
- GridSearchCV / RandomizedSearchCV for optimal performance

---

## 📉 Handling Class Imbalance

- SMOTE (Synthetic Minority Oversampling Technique)
- Class Weighting

---

## 📈 Evaluation Metrics

- Confusion Matrix
- ROC AUC Curve
- Precision, Recall, F1-Score

---

## 📌 Key Insights & Recommendations

- Drivers with decreasing income and ratings are more likely to churn.
- New drivers (low tenure) show a higher tendency to leave early.
- Targeted incentives can be introduced for high-risk drivers (based on model prediction).
- Invest in retention efforts rather than frequent rehiring, which is costlier.

---

## 📁 Project Structure

