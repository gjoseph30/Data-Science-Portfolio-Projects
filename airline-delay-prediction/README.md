# U.S. Airline Arrival Delay Analysis and Prediction

## Overview

This project analyzes U.S. airline on-time performance data from 2025 to identify patterns associated with arrival delays and evaluate whether pre-flight information can be used to predict flights arriving at least 15 minutes late.

The project combines large-scale data preparation, exploratory data analysis, feature engineering, and supervised machine learning. Logistic Regression and Random Forest models were evaluated using a stratified development sample while preserving the original class distribution.

## Project Objective

What patterns are associated with U.S. airline arrival delays, and how effectively can information available before departure predict whether a flight will arrive at least 15 minutes late?

## Data

The project uses 2025 U.S. airline on-time performance data.

Cancelled and diverted flights were excluded from the completed-flight analysis, and arrival delay was represented using the `ARR_DEL15` indicator:

- 0 = On time or less than 15 minutes late
- 1 = Arrived 15 or more minutes late

The final pre-flight modeling dataset contained:

**6,879,484 flights**

Target distribution:

- On time / less than 15 minutes late: 77.69%
- Delayed 15+ minutes: 22.31%

## Exploratory Data Analysis

Arrival delay rates were examined across several operational dimensions:

- Month
- Reporting airline
- Origin airport
- Scheduled departure time
- Day of week
- Flight distance

The analysis identified substantial variation in delay rates across carriers, airports, and departure periods.

### Scheduled Departure Time

Departure time showed one of the clearest relationships with arrival delays.

Delay rates increased throughout the day:

- Early Morning: 11.00%
- Morning: 16.69%
- Afternoon: 25.38%
- Evening: 31.82%
- Late Night: 27.44%

This pattern suggests that flights scheduled earlier in the day experienced substantially lower arrival-delay rates than flights departing later.

### Day of Week

Delay rates also varied by day.

Sunday had the highest delay rate at approximately 26.36%, while Tuesday had the lowest at approximately 18.39%.

### Flight Distance

Distance showed a smaller relationship with delay rates than departure time.

Flights between 1,000 and 1,499 miles had the highest delay rate among the distance groups analyzed at approximately 23.34%, while flights of 2,000 miles or more had a lower rate of approximately 20.69%.

## Modeling Dataset

Only variables that could reasonably be known before departure were included in the predictive models.

Features included:

- Month
- Day of week
- Reporting airline
- Origin airport
- Destination airport
- Scheduled departure time
- Scheduled arrival time
- Scheduled elapsed time
- Flight distance

Variables containing actual post-departure delay information were intentionally excluded to reduce target leakage.

## Model Development

A stratified sample of 1,000,000 flights was selected from the full modeling dataset for model development.

The sample was divided into:

- Training set: 800,000 flights
- Test set: 200,000 flights

The delayed-flight rate remained 22.31% in the development, training, and test sets.

A majority-class baseline that classified every flight as not delayed produced an accuracy of:

**77.69%**

Because of the class imbalance, accuracy alone was not considered sufficient for model evaluation.

## Logistic Regression

Logistic Regression was trained using class balancing, one-hot encoding for categorical features, and standardized numeric variables.

Results:

- Accuracy: 60.56%
- Precision: 30.99%
- Recall: 62.58%
- F1 Score: 0.4145
- ROC-AUC: 0.6512

Although its overall accuracy was lower than the majority-class baseline, the model identified approximately 63% of delayed flights.

## Random Forest

A class-balanced Random Forest classifier was also evaluated.

Results:

- Accuracy: 60.22%
- Precision: 31.09%
- Recall: 64.37%
- F1 Score: 0.4193
- ROC-AUC: 0.6681

The Random Forest produced slightly stronger recall, F1 score, and ROC-AUC than Logistic Regression.

## Model Comparison

The majority-class baseline achieved higher overall accuracy because most flights were not delayed. However, it had zero ability to identify delayed flights.

For this reason, recall, F1 score, and ROC-AUC provide more useful measures of predictive performance for the delayed-flight class.

Among the two predictive models, Random Forest provided the stronger overall discrimination, although performance remained moderate.

The results indicate that pre-flight schedule and route information contains useful predictive signal but is not sufficient by itself for highly accurate delay prediction.

## Feature Importance

Random Forest feature importance showed that scheduled timing variables were the strongest predictors.

The two most influential features were:

- Scheduled arrival time
- Scheduled departure time

Month and day of week also contributed predictive information, followed by scheduled elapsed time, distance, carrier, and airport-related variables.

These results are consistent with the exploratory analysis showing substantial differences in delay rates according to scheduled departure period.

## Key Findings

The project produced several important findings:

1. Arrival-delay risk varied substantially by scheduled departure time.
2. Evening flights experienced considerably higher delay rates than early-morning flights.
3. Delay rates differed across carriers, airports, and days of the week.
4. Flight distance had a comparatively modest relationship with delay rates.
5. Scheduled arrival and departure times were the strongest Random Forest predictors.
6. Random Forest slightly outperformed Logistic Regression on recall, F1 score, and ROC-AUC.
7. Pre-flight variables alone provided moderate predictive power, suggesting that additional operational and environmental information would be needed for stronger predictions.

## Limitations and Future Work

The predictive models intentionally use information available before departure. As a result, important real-time causes of delays—such as weather, air-traffic congestion, aircraft rotation, maintenance events, and developing operational disruptions—are not included.

Future work could incorporate:

- Weather conditions
- Airport congestion
- Previous aircraft delays
- Real-time operational information
- Additional model tuning
- Gradient-boosting models
- Probability-threshold optimization
- Precision-recall analysis
- Temporal validation

These additions could improve predictive performance while maintaining the goal of forecasting delays before they occur.

## Tools

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Logistic Regression
- Random Forest
- One-Hot Encoding
- Feature Scaling
- Jupyter Notebook

## Repository Contents

- `notebook/` — Jupyter Notebook containing data preparation, exploratory analysis, modeling, evaluation, and feature-importance analysis
- `reports/` — Final project report and presentation

## Skills Demonstrated

Large-Scale Data Analysis | Exploratory Data Analysis | Machine Learning | Classification | Logistic Regression | Random Forest | Class Imbalance | Feature Engineering | Model Evaluation | Feature Importance | Transportation Analytics | Python | Scikit-learn