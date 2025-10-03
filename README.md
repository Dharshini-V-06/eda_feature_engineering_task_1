# 📊 Calorie Expenditure Prediction

## 📌 Project Overview

This project focuses on predicting **calorie expenditure** using a dataset containing demographic and physiological information such as **Age, Sex, Height, Weight, Duration, Heart Rate, Body Temperature**, etc.

The workflow involves:

* Performing **Exploratory Data Analysis (EDA)** to understand the dataset.
* Applying **Feature Engineering** to prepare data for machine learning models.
* Building models to predict **Calories burned**.

---

## 📂 Dataset

The dataset is sourced from **Kaggle – Predict Calorie Expenditure**.

Dataset Link: [Predict Calorie Expenditure](https://www.kaggle.com/datasets/adilshamim8/predict-calorie-expenditure)
It typically includes the following features:

* `User_ID` : Unique identifier for individuals
* `Gender` : Male/Female
* `Age` : Age of individual
* `Height` : Height in cm
* `Weight` : Weight in kg
* `Duration` : Duration of exercise (minutes)
* `Heart_Rate` : Average heart rate during activity
* `Body_Temp` : Body temperature during activity
* `Calories` : **Target variable** – calories burned

## 📝 EDA Tasks

1. **Data Overview** – Inspect shape, column names, data types.
2. **Missing Values Check** – Identify and handle missing values.
3. **Statistical Summary** – Mean, median, standard deviation.
4. **Distribution Analysis** – Histograms for continuous variables.
5. **Categorical Analysis** – Count plots for categorical variables.
6. **Correlation Analysis** – Heatmap to check relationships.
7. **Target Distribution** – Histogram of `Calories`.

---

## 🔨 Feature Engineering

* **Missing Value Imputation** – Fill missing values with mean/median/mode.
* **Encoding Categorical Variables** – Convert `Gender` and age groups into numerical format.
* **Feature Scaling** – Standardize numerical features for ML models.
* **New Features**:

  * `BMI = Weight / (Height/100)^2`
  * `Duration x Heart_rate = duration*heart_rate`

---
## 📊 Visual Insights

Below are the key visualizations from the dataset and the insights gained:

1. **Distribution of Calories Burned**

   * Histogram shows that most people burn calories within a moderate range, with fewer extreme high-burn cases (possible outliers).

2. **Gender Distribution**

   * Count plot confirms the dataset has a balanced number of male and female participants (or highlights imbalance if skewed).

3. **Calories vs Weight**

   * Scatter plot shows no strong linear relation, but calorie expenditure may slightly vary with weight.
     
4. **Calories vs Height**

   * Scatter plot shows no strong linear relation, but calorie expenditure may slightly vary with Height.
     
5. **Boxplot of Calories by Gender**

   * Males generally show slightly higher calorie expenditure than females, but there is significant overlap.

6. **Pairplot of Key Features**

   * Confirms multicollinearity among `Weight`, `BMI`, and `Calories`.
   * Visualizes overall feature relationships.

---

## 📈 Results

* EDA insights on calorie expenditure factors.
* Preprocessed dataset ready for model training.
* Example ML models for calorie prediction.

---
