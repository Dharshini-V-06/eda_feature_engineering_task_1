# Calories Burn Prediction – EDA & Feature Engineering

##  Overview

This project performs **Exploratory Data Analysis (EDA)** and **Feature Engineering** on a dataset containing information about individuals’ exercise sessions (Age, Height, Weight, Duration, Heart Rate, etc.) to understand how these variables relate to **Calories burned**.
Both **train** and **test** datasets are explored and prepared for further model development.

---

## Dataset Description

### **Train Dataset**

| Column       | Description                           |
| :----------- | :------------------------------------ |
| `id`         | Unique identifier                     |
| `Sex`        | Gender (male/female)                  |
| `Age`        | Age in years                          |
| `Height`     | Height in centimeters                 |
| `Weight`     | Weight in kilograms                   |
| `Duration`   | Exercise duration (minutes)           |
| `Heart_Rate` | Average heart rate during exercise    |
| `Body_Temp`  | Body temperature during exercise (°C) |
| `Calories`   | Target variable — calories burned     |

### **Test Dataset**

Similar to the train dataset, but **without the `Calories`** column.

---

##  Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.preprocessing import PowerTransformer
import sympy as sp
```

---

##  Steps Performed

### **Data Loading & Inspection**

* Loaded both train and test CSV files using pandas.
* Checked dataset structure using `.info()` and `.describe()`.
* Verified there are **no missing values** and **no duplicate rows**.

###  **Exploratory Data Analysis (EDA)**

* Used `describe()` to understand data distribution and range.
* Verified that `Calories` ranges from **1 to 314**.
* Plotted distributions and boxplots for:

  * `Calories`, `Duration`, `Heart_Rate`, `Body_Temp`
  * Gender-based comparisons (`Sex` vs `Calories`)
  * Scatter plots for relationships (`Duration` vs `Calories`, `Duration x Heart_Rate` vs `Calories`).

---

##  Visualizations

###  Distributions

* KDE and histogram plots for key numerical features.
* Observed slight **right skewness** in `Calories` distribution.

###  Boxplots & Scatterplots

* **Boxplot:** Calories distribution across genders.
* **Scatterplots:** Calories vs Duration (weighted by Weight).
* Strong linear relationship between `Duration × Heart_Rate` and `Calories`.

###  Correlation Heatmap

* Highest correlation observed:

  * `Duration (0.96)`
  * `Heart_Rate (0.91)`
  * `Body_Temp (0.83)`
* Weak correlation for `Height` and `Weight`.

---

## Statistical Analysis

| Metric                       |  Value |
| :--------------------------- | -----: |
| **Mean Calories**            |  88.28 |
| **Median Calories**          |   77.0 |
| **Mode Calories**            |    7.0 |
| **% Above Average Calories** | 44.47% |

---

##  Feature Engineering

| Feature                 | Description                                                        |
| :---------------------- | :----------------------------------------------------------------- |
| `Sex_mapped`            | Encoded `male` → 0, `female` → 1                                   |
| `Calories_sqrt`         | Square-root transformation (reduced skewness to ≈ 0)               |
| `Body_Temp_transformed` | Power transformation using Yeo–Johnson                             |
| `BMI`                   | Calculated as `Weight / (Height/100)^2`, rounded to 2 decimals     |
| `Duration_x_HeartRate`  | Created interaction feature capturing intensity                    |
| `BMI_Category`          | Categorized BMI → Underweight / Normal / Overweight / Obese        |
| `Weight_bin`            | Quartile-based binning of weight → Low / Medium / High / Very High |

---

##  Key Insights

* **Calories** strongly depend on **Duration** and **Heart Rate**.
* **Body Temperature** also shows a positive relationship with Calories.
* **Weight and Height** have negligible correlation.
* Most individuals fall under **Normal BMI (62%)**.
* Dataset is clean, balanced, and ready for modeling.

---

##  Transformations Summary

| Feature     | Transformation                 | Result                  |
| :---------- | :----------------------------- | :---------------------- |
| `Calories`  | √ (Square Root)                | Normalized distribution |
| `Body_Temp` | PowerTransformer (Yeo–Johnson) | Reduced skewness        |
| `Sex`       | Label Encoding                 | Categorical → Numeric   |
| `Weight`    | Quartile Binning               | Weight Groups           |

---

##  Visual Summary

* Heatmaps, pie charts, bar charts, boxplots, and scatter plots used for visualization.
* Weight, BMI, and gender analyzed with respect to calories burned.

---

