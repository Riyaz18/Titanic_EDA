# 🛳️ Titanic Survival Prediction - Beginner EDA & Data Preprocessing

This notebook focuses on **Exploratory Data Analysis (EDA)** and **Data Preprocessing** for the Titanic dataset. As a beginner, I worked through understanding the dataset structure, handling missing values, uncovering patterns in survival, and preparing the data for modeling.

---

## 🔍 What I Did

### 1. 📊 Dataset Structure & Data Quality

- **Dataset Shape:** 891 rows, 12 columns
- **Feature Types:**
  - **Numerical:** Age, Fare, SibSp, Parch, Pclass, Survived, PassengerId
  - **Categorical:** Sex, Embarked
  - **Text:** Name, Ticket, Cabin

#### 🧼 Missing Values
- **Cabin:** 77% missing → Dropped (too sparse)
- **Age:** 20% missing → Imputed using **median**
- **Embarked:** 2 missing → Imputed using **mode** ('S')

📌 **Insight:** Data quality issues like missing values were handled through dropping or imputation.

---

### 2. 🎯 Target Variable (Survived)

- **Distribution:**
  - Survived = 0 (61.6%)
  - Survived = 1 (38.4%)
- Slightly imbalanced data

📌 **Insight:** Since the data is imbalanced, evaluation should not rely only on accuracy. Metrics like **precision**, **recall**, and **F1-score** are more meaningful.

---

### 3. 📈 Numerical Features

- **Age:**
  - Nearly normally distributed
  - Outliers present
  - Imputed and ready for standardization (e.g., `StandardScaler`)
- **Fare:**
  - Highly skewed, outliers exist
  - Suggested log transformation
- **SibSp / Parch:**
  - Mostly 0 or 1
  - Can be combined as **family size**

📌 **Insight:** Transformed/engineered numerical features to improve modeling.

---

### 4. 🧬 Categorical Features

- **Sex:** Strong correlation with survival
  - Female survival: ~74%
  - Male survival: ~19%
- **Pclass:**
  - 1st class: ~63%
  - 2nd class: ~47%
  - 3rd class: ~24%
- **Embarked:**
  - Cherbourg (C): ~55%
  - Queenstown (Q): ~39%
  - Southampton (S): ~34%

📌 **Insight:** Categorical features are very informative. Applied **encoding techniques** (e.g., one-hot encoding) for modeling.

---

### 5. 📊 Correlations & Feature Relationships

- **Correlations with Survived:**
  - Pclass: -0.34
  - Fare: +0.26
- **Feature Interactions:**
  - Strong patterns observed when combining Sex and Pclass
    - Female in 1st class: ~97% survival
    - Male in 3rd class: ~13.5% survival

📌 **Insight:** Created interaction features like `Sex_Pclass` to improve prediction.

---

## 🧠 Key Takeaways

### ✅ What I Learned:

- How to explore and clean real-world data.
- Importance of imputing missing values.
- Identifying valuable features for prediction.
- Understanding how social and economic status affected survival on the Titanic.

---

## 📌 The Story Behind the Data

The Titanic dataset tells a powerful story about how **gender**, **class**, and **social status** impacted survival during the disaster. Here's what I found:

- **Women in 1st class had the highest survival rate (~97%)**, showing clear prioritization.
- **Men in 3rd class had the lowest (~13.5%)**, highlighting the tragic inequality.
- **Cabin information was too sparse to use**, possibly due to poor record-keeping.
- **Sex** and **Pclass** were the strongest indicators of survival.

This project was a great way for me to learn the **basics of EDA**, **data cleaning**, and **feature engineering**, all crucial for building a predictive model.

---

## 💾 Next Steps

- Save the cleaned dataset.
- Train a machine learning model (e.g., logistic regression).
- Evaluate using precision, recall, and F1-score.
- Upload the notebook to **Kaggle** and **GitHub** to showcase my beginner journey.

---

## 📁 File Name

**`Titanic_Survival_Prediction.ipynb`**

---

*Thanks for reading! This was my beginner attempt at understanding the Titanic dataset and preparing it for a predictive model.*
