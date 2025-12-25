# Worcester-Bus-Travel-Time-Prediction-Model
The goal of this project was to build a machine learning model to predict actual WRTA bus travel time between stops using historical data. The project involved data cleaning, feature engineering, and comparing Linear Regression, Random Forest, and XGBoost, with Random Forest achieving the best performance.

The project was sourced from Kaggle with:
Rows: 115, 147 (Each row represents two different stops from a bus route, each includes the Bus_ID, scheduled and actual speeds, timestamps, route name, and service period.)
Features: 44 (reduced to 13 after cleaning)
Target Variable: RUNNING_TIME_ACT (Actual bus travel time between stops)

Data Cleaning and Preprocessing: 
There was a lot of preprocessing due to the sheer size and amount of data so I could make it suitable for modeling.
I dropped unnecessary/redundant columns.
I only chose 13 features to keep since these were the ones relevant to predicition of travel time.
Converted time fields (e.g., trip start time) to minutes after midnight
One-hot encoded categorical variables (ROUTE_NAME, DIRECTION_NAME, SERVICE_PERIOD)
removed rows with missing critical values and filled remaining NaNs using median/mode
Verified all features were numeric and model-ready

Models Used:
As a baseline Model I used simple linear regression. I didnt expect this to work since there are so many factors and linear regression struggles with anything other than linear.
I then tried Random Forest Regressor, this model handled non-linear relationshipss the best and feature interactions the best.
Finally I tried XGBoost Regressor, strong gradient boosting model but lower than Random Forest.

Results:
Random Forest performed best with an R² of 0.9995
XGBoost followed closely with an R² of 0.9986
Linear Regression achieved an R² of ~0.89, indicating linear assumptions were insufficient
Feature importance analysis showed that distance between stops, actual speed, and destination stop were the most influential predictors
Residual analysis confirmed tree-based models produced lower and more stable errors

The results show that WRTA buses are consistently late compared to scheduled times, typically by 1–4 minutes. Tree-based machine learning models, especially Random Forest, can predict actual travel time with high accuracy. This model could help improve WRTA scheduling accuracy and provide riders with more realistic arrival estimates.

I used Google Colab to create this.
