# Hospital Readmission Prediction

## Overview

This project uses machine learning to examine hospital readmission among patients with diabetes. The original dataset contains 101,766 hospital encounters and 50 variables representing patient demographics, diagnoses, medications, utilization history, and other encounter characteristics.

The primary objective was to develop a classification workflow for identifying patients who may be at greater risk of being readmitted within 30 days of discharge.

## Project Objective

Can patient and hospital encounter characteristics be used to predict whether a patient with diabetes will be readmitted within 30 days?

## Target Variable

The original readmission variable classified encounters into three categories:

- Readmitted within 30 days
- Readmitted after 30 days
- Not readmitted

For predictive modeling, the outcome was transformed into a binary classification problem focused on identifying readmission within 30 days.

The original dataset contained 11,357 encounters classified as readmitted within 30 days.

## Methods

The project includes:

- Data cleaning and preprocessing
- Missing-value analysis
- Feature selection and transformation
- Categorical-variable encoding
- Exploratory data analysis
- Class-imbalance evaluation
- Train/test data preparation
- Random Forest classification
- Model performance evaluation

## Tools

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## Model Evaluation

Model performance was evaluated using classification metrics rather than relying solely on overall accuracy. This is particularly important because 30-day readmissions represent a minority of the observations in the dataset.

Evaluation included measures such as:

- Precision
- Recall
- F1 score
- Confusion matrix
- ROC-AUC

These metrics provide a more complete assessment of the model's ability to distinguish patients who experienced a 30-day readmission from those who did not.

## Key Takeaways

The project demonstrates an end-to-end healthcare machine-learning workflow, from raw-data preparation and missing-value analysis through feature engineering, classification, and model evaluation.

The analysis also highlights the challenges associated with predicting relatively infrequent healthcare outcomes. Model performance should therefore be interpreted in the context of class imbalance, false positives, false negatives, and the limitations of the available data.

The model is an analytical and educational demonstration and should not be interpreted as a clinical decision-making tool.

## Ethical Considerations

Healthcare predictive models require careful consideration of privacy, fairness, bias, interpretability, and the potential consequences of incorrect predictions.

Patient data should be appropriately protected and de-identified, and predictive models should be validated across populations before consideration for real-world clinical use.

## Repository Contents

- `notebook/` — Jupyter Notebook containing data preparation, exploratory analysis, and predictive modeling
- `reports/` — Final project report and presentation

## Skills Demonstrated

Machine Learning | Random Forest | Classification | Healthcare Analytics | Data Cleaning | Feature Engineering | Model Evaluation | Python | Scikit-learn