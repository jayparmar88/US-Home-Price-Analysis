# US Home Price Analysis :

## Project Overview

This project aims to build a data science model to analysis US home prices using publicly available data. The project uses the S&P Case-Shiller Home Price Index (CSUSHPISA) as a proxy for home prices and explores various regression models to understand the key factors influencing home price trends over the last 20 years.

## Data Sources

The project utilizes data from the Federal Reserve Economic Data (FRED) database, specifically the following datasets:

- **CSUSHPISA:** Case-Shiller U.S. National Home Price Index (Target Variable)
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
5. **Model Building and Evaluation:** The following regression models are trained and evaluated:
    - Linear Regression
    - Elastic Net Regression
    - Decision Tree Regression
    - Random Forest Regression
   Model performance is assessed using Mean Squared Error (MSE) and R-squared (R2). Scatter plots of actual vs. predicted home prices are generated for visual assessment.
6. **Feature Importance Analysis:** For Decision Tree and Random Forest models, feature importance scores are calculated and analyzed to understand the relative influence of each feature on predictions.

## Results

- **Model Comparison:** Random Forest Regression consistently outperforms other models, achieving the lowest MSE and highest R-squared.
- **Key Factors:** The most influential features in predicting home prices are:
    - MSPUS (Median Sales Price of Houses Sold)
    - TTLCONS (Total Construction Spending)
    - GDP (Gross Domestic Product)
    - POPTHM (Population)

## Conclusion

The project demonstrates the effectiveness of using machine learning, particularly Random Forest Regression. The analysis highlights the importance of economic growth, housing market activity, and demographic factors in driving home price trends.

## Repository Structure

- `CSUSHPISA.csv`, `FEDFUNDS.csv`, `HOUST.csv`, `MSACSR.csv`, `PERMIT.csv`, `POPTHM.csv`, `UNRATE.csv`, `GDP.csv`, `TTLCONS.csv`, `MSPUS.csv`: Data files.
- `US_home_price_analysis.ipynb`: Python script containing the data analysis and model building code.
- `README.md`: This file.

## Author

Jay Parmar
