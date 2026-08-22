# NBA Hidden Gems: Machine Learning for Player Scouting

## Overview

This project develops a machine-learning approach to NBA player scouting using player performance statistics. The goal was to identify underutilized players whose statistical profiles suggest potential value that may not be captured by traditional measures of player role or visibility.

The project combines unsupervised and supervised machine learning to explore player similarities, identify performance-based groups, and classify potential "Hidden Gem" players.

## Project Objective

Can NBA player performance statistics be used to identify underutilized players who share characteristics with higher-performing talent?

## Methods

The project includes:

- Data cleaning and preprocessing
- Exploratory data analysis
- Feature engineering
- Principal Component Analysis (PCA)
- K-Means clustering
- Class-imbalance treatment using SMOTE
- Random Forest classification
- Model evaluation using precision, recall, F1 score, and accuracy

## Tools

- Python
- Pandas
- Scikit-learn
- PCA
- K-Means
- Random Forest
- SMOTE
- Jupyter Notebook
- Data visualization libraries

## Key Findings

The analysis demonstrated that NBA player statistics can be used to identify performance-based player groups beyond traditional position labels.

After addressing class imbalance with SMOTE, the Random Forest model achieved approximately:

- 90% overall accuracy
- 67% precision for the Hidden Gem class
- 100% recall for the Hidden Gem class
- 0.80 F1 score for the Hidden Gem class

The results suggest that machine learning can supplement traditional scouting by highlighting players whose statistical profiles warrant additional evaluation. Validation using additional seasons and data would be necessary before applying the model to real-world personnel decisions.

## Repository Contents

- `notebook/` — Jupyter Notebook containing data preparation, exploratory analysis, feature engineering, and machine-learning models
- `reports/` — Final project report and supporting documentation

## Skills Demonstrated

Machine Learning | PCA | K-Means Clustering | Random Forest | SMOTE | Feature Engineering | Model Evaluation | Sports Analytics | Python