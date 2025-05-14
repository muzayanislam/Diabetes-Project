
# Exploratory Study of Diabetes Indicators in Medical Data

This project performs data preprocessing, data cleaning, and exploratory data analysis (EDA) on the Pima Indians Diabetes Dataset to prepare it for machine learning tasks. The dataset contains diagnostic measurements for female patients and aims to predict whether a patient has diabetes.




## Dataset Information

- **Source:** Pima Indians Diabetes Database

- **Observations:** 768  
- **Features:** 9 (including the target variable `Outcome`)  
- **Target Variable:** `Outcome` — 1 indicates diabetes, 0 indicates no diabetes.

## 🔧 Data Preprocessing Steps

### ✅ Initial Checks

- Dataset loaded using `pandas.read_csv()`.
- Verified no missing values using `.info()` and `.isnull().sum()`.
- Checked for duplicate rows — none found.

### ⚠️ Handling Invalid Zero Values

Certain features contain biologically implausible zero values:

- `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, `BMI`

**Steps Taken:**

- Replaced zeroes with `np.nan`
- Visualized missing data using the `missingno` library
- Imputed missing values using column means
## 📊 Exploratory Data Analysis (EDA)

### ⚖️ Class Distribution
- Visualized using `sns.countplot()`
- **Result:** Imbalance observed  
  - 500 non-diabetic  
  - 268 diabetic

### 📈 Univariate Analysis
- Used histograms to analyze feature distributions
- Applied boxplots to detect outliers

### 🔁 Bivariate Analysis
- Grouped histograms by `Outcome` to observe patterns
- Compared mean values of features by `Outcome`

### 💡 Key Insights
Diabetic patients tend to have:
- Higher **glucose**, **insulin**, and **BMI**
- More **pregnancies**
- Higher **diabetes pedigree function**
- Older **age**
## 📉 Summary Statistics (Post-Cleaning)

| Feature         | Mean (Diabetic) | Mean (Non-Diabetic) |
|------------------|------------------|-----------------------|
| Glucose         | 142.17           | 110.71                |
| BloodPressure   | 75.15            | 70.94                 |
| BMI             | 35.38            | 30.89                 |
| Age             | 37.07            | 31.19                 |

##  🤖 Model Training & Evaluation

### 🧪 Train-Test Split

- Dataset split into training and testing sets using an 80/20 ratio.
- Features (`X`) and target (`y`) separated prior to splitting.

---

### ⚙️ Feature Scaling

- Standardized feature values using `StandardScaler` to ensure uniform scale across models.

---

### 📚 Classification Models Applied

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Decision Tree Classifier
- Random Forest Classifier

Each model was trained on the scaled training data and evaluated on the test data.

---

### 🧠 Model Predictions

- Predictions made using each trained model on the test set.
- Outputs stored for evaluation metrics and performance comparison.

---

### 📈 Evaluation Metrics

- Confusion Matrices visualized using heatmaps for all models.
- Key metrics computed:
  - **Accuracy**
  - **Precision**
  - **Recall**
  - **F1-Score**
  - **Specificity**

Models ranked based on accuracy and overall performance.