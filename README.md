# US Home Price Analysis :

## Project Overview

This project aims to build a data science model to analysis US home prices using publicly available data. The project uses the S&P Case-Shiller Home Price Index (CSUSHPISA) as a proxy for home prices and explores various regression models to understand the key factors influencing home price trends over the last 20 years.

## Data Sources

The project utilizes data from the Federal Reserve Economic Data (FRED) database, specifically the following datasets:
- [Dataset Link]([https://fred.stlouisfed.org/series/CSUSHPISA](https://fred.stlouisfed.org/))

°※ **Target Variable:**
- **CSUSHPISA:** Case-Shiller U.S. National Home Price Index (Target Variable)

 **Predictor Variables (Features):**
- **HOUST:** New Privately-Owned Housing Units Started: Total Units
- **MSACSR:** Monthly Supply of New Houses in the United States
- **PERMIT:** New Privately-Owned Housing Units Authorized in Permit-Issuing Places: Total Units
- **UNRATE:** Unemployment Rate
- **POPTHM:** Population (in thousands)
- **FEDFUNDS:** Federal Funds Effective Rate (Interest Rate)
- **GDP:** Gross Domestic Product
- **TTLCONS:** Total Construction Spending: Total Construction in the United States
- **MSPUS:** Median Sales Price of Houses Sold for the United States

## Methodology

1. **Data Loading and Merging:** The datasets are loaded into pandas DataFrames and merged based on the 'DATE' column.
2. **Data Filtering and Preprocessing:** The merged DataFrame is filtered to include data from 2004-01-01 to 2023-12-01. Missing values are handled using forward fill (`ffill`).
3. **Exploratory Data Analysis (EDA):**
    - Time series plots are generated for each feature to visualize trends and patterns over time.
    - Histograms are created to examine the distribution of each feature.
    - A correlation matrix is plotted to identify potential multicollinearity between features.
4. **Feature Scaling:** The features are standardized using `StandardScaler` to ensure they have a mean of 0 and a standard deviation of 1.
5. **Model Building:** The following regression models are trained and evaluated:
    - Linear Regression
    - Elastic Net Regression
    - Decision Tree Regression
    - Random Forest Regression
6. **Model Evaluation:** The models were compared based on their:
    - Mean Squared Error (MSE)
    - R-squared
    - Actual vs. Predicted Plots: To visualize prediction accuracy.
    - Feature Importance (for Tree-based models)
    - Coefficient Interpretation (for Linear models)

## Results

- **Model Comparison:** Random Forest Regression consistently outperforms other models, achieving the lowest MSE and highest R-squared.
- **Key Factors:** The most influential features in predicting home prices are:
    - MSPUS (Median Sales Price of Houses Sold)
    - TTLCONS (Total Construction Spending)
    - GDP (Gross Domestic Product)
    - POPTHM (Population)

## Conclusion

The project demonstrates the effectiveness of using data science in analyzing and predicting US home prices. The analysis highlights the importance of economic growth, housing market activity, and demographic factors in driving home price trends.

## Repository Structure

- `README.md`: This file.
- `CSUSHPISA.csv`, `FEDFUNDS.csv`, `HOUST.csv`, `MSACSR.csv`, `PERMIT.csv`, `POPTHM.csv`, `UNRATE.csv`, `GDP.csv`, `TTLCONS.csv`, `MSPUS.csv`: Data files.
- `US_home_price_analysis.ipynb`: Jupyter Notebook containing the Python code for data cleaning, EDA, model building, and evaluation.
