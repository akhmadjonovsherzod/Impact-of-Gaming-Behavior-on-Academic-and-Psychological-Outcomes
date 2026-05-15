# Impact of Gaming Behavior on Academic and Psychological Outcomes

**Big Data Analysis: Data Science Project**
Akhmadjonov Sh

---

## Project Overview

This project investigates how gaming behavior affects academic performance and psychological well-being among 1005 individuals. The dataset contains 39 features covering gaming habits, psychological scores, health metrics, and demographic information. Machine learning models including clustering, regression, and classification are applied to uncover patterns and test predictive relationships.

---

## Dataset

| File | Description |
|------|-------------|
| `data_4.csv` | Main dataset: 1005 rows, 39 columns |
| `data_4-2.txt` | Dataset description and feature documentation |

> The dataset files do not need to be submitted. The notebook reads `data_4.csv` directly.

**Key features include:** age, income, daily\_gaming\_hours, weekly\_sessions, sleep\_hours, stress\_level, anxiety\_score, depression\_score, academic\_performance, addiction\_level, and more.

---

## Project Structure

```
gaming_impact_final.ipynb   Main Jupyter Notebook with all code, outputs, and explanations
README.md                   This file
```

---

## How to Run

1. Open `gaming_impact_final.ipynb` in [Google Colab](https://colab.research.google.com) or Jupyter Notebook.
2. Upload `data_4.csv` when prompted by the file upload cell.
3. Run all cells from top to bottom in order.

All required libraries are available in the standard Colab environment. No additional installation is needed.

---

## Notebook Sections

| Section | Description |
|---------|-------------|
| 1. Data Loading | Load the CSV file and import all libraries |
| 2. Dataset Overview | Inspect rows, data types, and summary statistics |
| 3. Data Quality Check | Verify no missing values or duplicate rows |
| 4. Data Preprocessing | Encode gender, bin addiction level, define feature sets, split and scale data |
| 5. Data Visualization | Five figures exploring distributions, correlations, and group differences |
| 6. Clustering | K-Means (with elbow method) and Hierarchical (with dendrogram) |
| 7. Regression | Linear Regression and Random Forest Regression predicting academic performance |
| 8. Classification | Logistic Regression and Random Forest Classifier predicting addiction category |
| 9. Model Evaluation Summary | Side-by-side comparison of all model metrics |
| 10. Conclusion | Summary of findings, analysis, and reflection on challenges |

---

## Methods Used

### Preprocessing
- **OneHotEncoder**: converts the categorical gender column into binary columns (gender\_Female, gender\_Male, gender\_Other)
- **Quantile binning**: converts continuous addiction\_level into three balanced categories: Low, Medium, High
- **LabelEncoder**: encodes addiction category strings into integers (0, 1, 2)
- **StandardScaler**: normalizes all numeric features to zero mean and unit variance, fitted only on training data

### Visualizations
1. Distribution of Academic Performance (histogram with KDE)
2. Full correlation heatmap across all numeric features
3. Daily Gaming Hours vs Academic Performance (scatter plot)
4. Academic Performance by Addiction Category (boxplot)
5. Psychological score correlations: anxiety, depression, stress, addiction (focused heatmap)

### Clustering
- **K-Means**: optimal K selected using the Elbow Method, K=3 applied to full scaled feature set
- **Hierarchical (Agglomerative)**: Ward linkage, dendrogram plotted on 100-row sample, K=3 applied to full dataset

### Regression (target: academic\_performance)
- Linear Regression
- Random Forest Regression (100 estimators)
- Metrics: MAE, RMSE, R2

### Classification (target: addiction\_category\_encoded)
- Logistic Regression (max\_iter=1000)
- Random Forest Classifier (100 estimators)
- Metrics: Accuracy, Precision, Recall, F1-score per class, Confusion Matrix

---

## Results Summary

### Regression

| Model | MAE | RMSE | R2 |
|-------|-----|------|----|
| Linear Regression | ~11.38 | ~14.21 | ~-0.046 |
| Random Forest Reg. | ~11.29 | ~14.23 | ~-0.049 |

Both models produce a negative R2, meaning academic performance cannot be reliably predicted from gaming features alone. This is consistent with the near-zero correlations observed in the EDA phase.

### Classification

| Model | Accuracy |
|-------|----------|
| Logistic Regression | ~67.2% |
| Random Forest Clf. | ~64.7% |

Logistic Regression slightly outperforms Random Forest. Both models classify the Low addiction group most accurately and struggle most with the High group.

---

## Key Findings

- Gaming behavior features show very weak linear relationships with academic performance.
- Psychological indicators (anxiety, depression, stress) are largely independent of addiction level in this dataset.
- K-Means clustering identifies three reasonably balanced groups, while Hierarchical clustering reveals one small distinct subgroup (~38 rows).
- Classification accuracy around 65 to 67% suggests that addiction level can be partially predicted from behavioral and demographic features, but the signal is modest.

---

## Dependencies

All libraries used are available in the standard Google Colab environment:

```
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
```

---

## Author

Akhmadjonov Sh
Big Data Analysis: Data Science Project
