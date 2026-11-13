# Predicting Sleep Disorders Using Machine Learning

An end-to-end Machine Learning classification project that analyzes demographic, lifestyle, sleep, and cardiovascular indicators to predict sleep disorder categories.

## Project Overview

Sleep disorders such as Insomnia and Sleep Apnea can affect an individual's health, sleep quality, and daily activities.

This project develops a multiclass classification system to predict three sleep-disorder categories:

- **None**
- **Insomnia**
- **Sleep Apnea**

The objective is to investigate patterns in health and lifestyle data, develop predictive models, compare their performance, and identify a suitable classification approach.

This project is intended for educational and analytical purposes, not clinical diagnosis.

## Business Problem

Healthcare organizations may have access to demographic information, lifestyle characteristics, sleep metrics, and basic health indicators. Analyzing these factors can help identify patterns associated with recorded sleep-disorder categories.

The project investigates whether Machine Learning can identify these patterns and support non-diagnostic screening research.

## Project Objectives

- Perform comprehensive Exploratory Data Analysis (EDA).
- Investigate data quality, duplicate records, and conflicting labels.
- Analyze outliers and justify treatment decisions.
- Develop meaningful features from existing variables.
- Prevent data leakage during preprocessing and model development.
- Train and compare multiple classification algorithms.
- Address class imbalance and optimize model performance.
- Evaluate generalization, fairness, and model interpretability.
- Save and test the final prediction pipeline.
- Develop a reusable model-monitoring framework.

## Dataset Information

**Dataset:** Sleep Health and Lifestyle Dataset

| Property | Details |
|---|---|
| Records | 374 |
| Original features | 13 |
| Target variable | Sleep Disorder |
| Problem type | Multiclass Classification |
| Target classes | None, Insomnia, Sleep Apnea |

The dataset includes demographic, lifestyle, sleep-related, and cardiovascular attributes.

**Target variable:** `Sleep Disorder`

The target contains three categories: None, Insomnia, and Sleep Apnea.

Dataset file: `Sleep_health_and_lifestyle_dataset.csv`

Note: The dataset is not included in this repository. Obtain it from the original dataset source and follow its applicable usage license.

## Machine Learning Workflow

The project follows a structured end-to-end Machine Learning workflow.

### 1. Data Loading and Inspection
- Dataset loading and structural inspection.
- Data types and statistical summaries.
- Missing-value and duplicate analysis.
- Target-label verification.

### 2. Data Quality Assessment
- Duplicate record investigation.
- Conflicting-label analysis.
- Identifier and grouping investigation.
- Validation strategy design.

### 3. Leakage-Resistant Validation
- Group-independent holdout partition.
- Repeated group-aware cross-validation.
- Locked test-set evaluation.
- Validation integrity checks.

### 4. Exploratory Data Analysis
- Univariate and multivariate analysis.
- Numerical and categorical feature analysis.
- Target distribution analysis.
- Demographic and lifestyle patterns.
- Sleep and cardiovascular indicator analysis.
- Correlation and feature relationships.

### 5. Outlier Analysis
- IQR-based detection.
- Z-score and robust MAD analysis.
- Isolation Forest and Local Outlier Factor.
- Comparison of clipping and scaling strategies.
- Evidence-based outlier treatment decisions.

### 6. Data Preprocessing and Feature Engineering
- Data cleaning and transformation.
- Blood-pressure feature extraction.
- Feature engineering.
- Numerical scaling and categorical encoding.
- Feature selection.
- Leakage prevention through pipelines.

### 7. Model Development

Eight classification algorithms are trained and compared:

1. Decision Tree
2. Random Forest
3. Logistic Regression
4. Support Vector Machine (SVM)
5. K-Nearest Neighbours (KNN)
6. Extra Trees
7. HistGradientBoosting
8. XGBoost

### 8. Model Optimization
- Class imbalance investigation.
- Class weighting and resampling experiments.
- Hyperparameter tuning.
- Nested cross-validation.
- Ensemble learning.
- Model selection and probability calibration analysis.

### 9. Model Evaluation
- Accuracy
- Balanced Accuracy
- Precision
- Recall
- Macro F1-Score
- Weighted F1-Score
- Confusion Matrix
- ROC-AUC and additional classification metrics.

### 10. Advanced Model Analysis
- Overfitting and underfitting analysis.
- False-negative investigation.
- Feature importance and SHAP analysis.
- Subgroup and fairness analysis.
- Distribution-shift investigation.
- Model interpretability.

### 11. Deployment Readiness and Monitoring
- Save the complete fitted prediction pipeline.
- Develop a reusable prediction function.
- Execute prediction tests.
- Create a model-monitoring plan.
- Generate dashboard-ready CSV exports and documentation.

## Model Evaluation Results

The final selected model is a Support Vector Machine (SVM) with a linear kernel.

**Final holdout test-set classification report:**

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Insomnia | 1.00 | 0.20 | 0.33 |
| None | 0.78 | 0.98 | 0.87 |
| Sleep Apnea | 0.89 | 0.94 | 0.92 |
| **Overall Accuracy** | | **0.82** | |

**Macro F1-Score:** 0.71

The model performs well in identifying the None and Sleep Apnea categories. However, Insomnia recall remains low, indicating that the model misses a substantial proportion of actual Insomnia cases.

These results demonstrate why evaluating multiple metrics is important, particularly when working with imbalanced healthcare-related datasets.

## Key Technical Considerations

- Group-aware validation to reduce duplicate-profile leakage.
- Learned preprocessing contained within cross-validation pipelines.
- Outlier treatment based on experimental evidence.
- Minority-class performance analysis.
- Untouched holdout test evaluation.
- Explicit investigation of model limitations and generalization.

## Technologies and Libraries

**Programming Language**
- Python

**Data Analysis**
- Pandas
- NumPy
- SciPy

**Data Visualization**
- Matplotlib
- Seaborn

**Machine Learning**
- Scikit-learn
- Imbalanced-learn
- XGBoost

**Model Interpretation**
- SHAP
- Permutation Importance

**Development Environment**
- Jupyter Notebook
- Google Colab / Kaggle

## Repository Structure

```text
Predicting-Sleep-Disorders/
│
├── Predicting_Sleep_Disorder.ipynb
├── README.md
└── requirements.txt
```

## How to Run the Project

1. Clone the repository:

```bash
git clone https://github.com/Satish-Tarak/Predicting-Sleep-Disorders.git
```

2. Navigate to the project directory:

```bash
cd Predicting-Sleep-Disorders
```

3. Install the required libraries:

```bash
pip install numpy pandas scipy matplotlib seaborn scikit-learn imbalanced-learn xgboost shap cloudpickle python-docx
```

4. Download the dataset from its original source.

5. Place the dataset in your working directory or update the dataset path in the notebook.

6. Open the notebook:

```bash
jupyter notebook Predicting_Sleep_Disorder.ipynb
```

7. Execute the notebook sequentially.

## Limitations and Future Scope

- The dataset contains only 374 records, limiting the amount of independent information available.
- Repeated feature profiles and conflicting labels create challenges for reliable prediction.
- Insomnia recall is relatively low and requires further investigation.
- External-dataset and temporal validation are unavailable because the dataset does not provide the required information.
- The model requires evaluation on larger, independent, and more diverse datasets before any real-world application.

Future improvements could include external validation, larger datasets, additional clinical features, and further investigation of minority-class prediction performance.

## Conclusion

This project demonstrates a comprehensive Machine Learning workflow for sleep-disorder classification, covering data exploration, data quality, feature engineering, leakage-resistant validation, model comparison, optimization, interpretation, and monitoring.

Beyond model accuracy, the project emphasizes responsible evaluation, reproducibility, and transparent reporting of limitations.

**Disclaimer:** This project is developed exclusively for educational and research purposes. Predictions should not be used as a substitute for professional medical advice, diagnosis, or treatment.

---

**Project:** Predicting Sleep Disorders Using Machine Learning  
**Repository:** [GitHub – Predicting Sleep Disorders](https://github.com/Satish-Tarak/Predicting-Sleep-Disorders)
