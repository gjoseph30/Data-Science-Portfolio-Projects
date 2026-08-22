# U.S. Retail Sales Forecasting

## Overview

This project develops a time-series forecasting workflow for monthly U.S. retail sales.

The analysis examines nearly three decades of retail-sales history to identify long-term trends, recurring seasonal behavior, and unusual movements associated with the COVID-19 period. A seasonal forecasting model was then trained and evaluated against a 12-month holdout period.

## Project Objective

Can historical monthly U.S. retail sales patterns be used to forecast future retail activity using seasonal time-series modeling?

## Dataset

The dataset contains monthly U.S. retail sales observations from January 1992 through December 2021.

The original data were stored in wide format, with one row per year and separate columns for each month. The data were transformed into a chronological monthly time series for analysis and forecasting.

After reshaping, the dataset contained 360 monthly observations.

## Exploratory Analysis

Initial visualization revealed several important characteristics:

- A strong long-term upward trend in retail sales
- Recurring seasonal fluctuations
- Noticeable disruption during the COVID-19 period
- A sharp decline followed by a substantial rebound during 2020

These characteristics supported the use of a forecasting model capable of accounting for both trend and seasonality.

## Train/Test Strategy

The historical series was divided chronologically rather than randomly to preserve the temporal structure of the data.

Training period:

**January 1992 – June 2020**

Test period:

**July 2020 – June 2021**

The final 12-month period was withheld from model training and used to compare forecasts with actual observations.

## Forecasting Model

The workflow was designed to attempt automatic ARIMA model selection when the `pmdarima` package was available.

Because `pmdarima` was not available in the development environment, the analysis used a seasonal SARIMAX model:

**SARIMAX(1,1,1) × (1,1,1,12)**

The seasonal period of 12 represents annual seasonality in monthly retail-sales data.

## Model Evaluation

Forecast performance was evaluated by comparing predicted sales with actual observations during the 12-month test period.

The model produced a test:

**RMSE = 59,819.07**

The forecast visualization was also used to compare the predicted trajectory against actual retail-sales behavior.

## Interpretation

The analysis demonstrates both the usefulness and difficulty of forecasting economic activity during periods of substantial disruption.

Historical retail-sales data contain clear trend and seasonal structure that can support time-series modeling. However, extraordinary events such as the COVID-19 pandemic can produce abrupt structural changes that historical patterns alone may not fully capture.

For this reason, forecast error should be interpreted in the context of the unusual economic conditions represented in the test period.

## Methods

The project includes:

- Data reshaping
- Date/time transformation
- Time-series visualization
- Trend and seasonality analysis
- Chronological train/test splitting
- Seasonal ARIMA modeling
- SARIMAX forecasting
- Out-of-sample model evaluation
- RMSE calculation
- Actual-versus-forecast visualization

## Tools

- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn
- Jupyter Notebook

## Limitations and Future Work

The forecasting model relies primarily on historical retail-sales patterns and does not incorporate external economic variables.

Future analysis could evaluate additional forecasting approaches and incorporate explanatory variables such as:

- Inflation
- Consumer confidence
- Unemployment
- Interest rates
- Disposable income
- Holiday effects
- Economic shocks

Additional models could also be compared using multiple evaluation metrics and rolling time-series validation.

## Repository Contents

- `data/` — Monthly U.S. retail sales dataset
- `notebook/` — Jupyter Notebook containing data preparation, modeling, forecasting, and evaluation
- `reports/` — Supporting project report

## Skills Demonstrated

Time-Series Analysis | Forecasting | SARIMAX | Seasonal Modeling | Pandas | Statsmodels | Model Evaluation | Data Visualization | Python