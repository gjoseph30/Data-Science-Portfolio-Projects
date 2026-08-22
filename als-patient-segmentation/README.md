# ALS Patient Segmentation Using K-Means Clustering

## Overview

This project applies unsupervised machine learning to an anonymized dataset containing clinical characteristics of patients with Amyotrophic Lateral Sclerosis (ALS).

The objective was to explore whether patients could be grouped according to similarities across their available clinical measurements without using a predefined outcome variable.

The analysis uses K-Means clustering, silhouette analysis, and Principal Component Analysis (PCA) to investigate potential patient segments.

## Project Objective

Can unsupervised machine learning identify meaningful groupings among ALS patients based on similarities in their clinical characteristics?

## Dataset

The dataset contains:

- 2,223 patient observations
- 101 original variables
- Clinical and functional measurements related to ALS patients

Examples of available features include age, laboratory measurements, ALS Functional Rating Scale information, and measures related to physical functioning.

Patient identifier fields were excluded from clustering because they do not represent clinical characteristics.

## Data Preparation

The preprocessing workflow included:

- Removing `ID` and `SubjectID`
- Retaining numeric analytical features
- Evaluating missing values
- Median imputation where necessary
- Standardizing features using `StandardScaler`

Standardization was particularly important because K-Means clustering relies on distance calculations and the dataset contains measurements represented on different numerical scales.

## Cluster Selection

K-Means models were evaluated using values of K from 2 through 10.

The silhouette score was used to compare cluster separation and cohesion.

The highest silhouette score occurred at:

**K = 2**

with a silhouette score of approximately:

**0.079**

Because this score is low, the resulting clusters should be interpreted as broad exploratory groupings rather than clearly separated patient subtypes.

## Final Clustering Results

The final K-Means model produced two nearly equal-sized groups:

- Cluster 0: 1,111 observations
- Cluster 1: 1,112 observations

Although the algorithm divided the observations into two groups, the low silhouette score indicates substantial similarity or overlap between them.

## PCA Visualization

Principal Component Analysis was used to reduce the high-dimensional feature space to two dimensions for visualization.

The first two principal components explained approximately:

- PC1: 11.3% of variance
- PC2: 6.4% of variance

Together, the first two components represented approximately 17.8% of the total variance.

The PCA scatterplot provided a visual representation of the two K-Means clusters but also demonstrated that the groups were not strongly separated.

## Methods

The project includes:

- Data cleaning
- Identifier removal
- Missing-value handling
- Feature standardization
- K-Means clustering
- Silhouette analysis
- Cluster selection
- Principal Component Analysis
- Dimensionality reduction
- Cluster visualization

## Tools

- Python
- Pandas
- NumPy
- Scikit-learn
- K-Means
- PCA
- Matplotlib
- Seaborn
- Jupyter Notebook

## Key Findings

The analysis identified two broad groups within the dataset, but the clustering structure was weak.

The best silhouette score of approximately 0.079 indicates that the observations do not form strongly separated clusters based on the features and preprocessing approach used in this analysis.

This is an important analytical result: unsupervised algorithms can always assign observations to clusters, but the existence of assigned clusters does not necessarily mean that meaningful natural subgroups exist in the underlying population.

## Limitations and Future Work

The analysis is exploratory and does not establish clinically meaningful ALS patient subtypes.

Potential extensions include:

- Clinical interpretation of the variables that most distinguish the clusters
- Alternative clustering algorithms
- Feature selection before clustering
- Additional dimensionality-reduction methods
- External validation
- Analysis of disease progression
- Collaboration with clinical subject-matter experts

Any clinical interpretation would require appropriate validation and professional medical expertise.

## Repository Contents

- `data/` — ALS dataset used for the analysis
- `notebook/` — Jupyter Notebook containing preprocessing, clustering, evaluation, and PCA visualization
- `reports/` — Supporting project report

## Skills Demonstrated

Unsupervised Machine Learning | K-Means Clustering | PCA | Patient Segmentation | Silhouette Analysis | Feature Scaling | Data Preprocessing | Healthcare Analytics | Python | Scikit-learn