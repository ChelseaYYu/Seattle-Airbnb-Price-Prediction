# Airbnb Price Prediction for Seattle

## Project Overview
This project aims to analyze Airbnb rental prices in Seattle to uncover insights on demand fluctuations and occupancy rates. The analysis focuses on determining peak seasons, price variability, and average occupancy rates, helping stakeholders optimize pricing and improve rental strategies.

## Libraries Used
pandas: Data manipulation and analysis

numpy: Numerical computing

scikit-learn: Machine learning and data preprocessing

matplotlib: Data visualization

seaborn: Statistical data visualization

xgboost: Implementation of the XGBoost algorithm

category_encoders: Encoding categorical variables

nltk: Natural Language Processing

## Files in the Repository
README.md: This file, providing an overview of the project, the libraries used, and the results of the analysis.

Airbnb_final.ipynb: Jupyter notebook containing the complete analysis, including data preprocessing, exploratory data analysis (EDA), feature engineering, model building, and evaluation.

The [data](https://www.kaggle.com/datasets/airbnb/seattle/data) used in this project is sourced from the publicly available Airbnb dataset for Seattle, covering calendar years and listing details.

calendar.csv: Booking and availability data for Airbnb listings in Seattle.

listings.csv: Detailed information about Airbnb listings in Seattle.

reviews.csv: Review data for Airbnb listings in Seattle.

## Business Questions
1. **Demand Analysis**
   - What are the peak seasons for Airbnb rentals in Seattle?
   - How do rental prices fluctuate throughout the year?
   - What is the average occupancy rate by season or month?

2. **Supply Analysis**
   - How many listings are available in each neighborhood?
   - What types of properties are most common (e.g., entire homes vs. private rooms)?
   - Are there enough listings to meet the demand in high-traffic periods?

3. **Pricing Strategies**
   - What factors affect the pricing of listings?

## Data Preprocessing
### Encoding and Imputing
- **Encoding**: Categorical variables such as `cancellation_policy`, `property_type`, `room_type`, and `bed_type` are encoded using one-hot encoding to convert them into a format suitable for modeling.
- **Imputing**:
  - Numerical attributes are imputed using the median to handle outliers.
  - Categorical attributes are imputed with the most frequent category to maintain the distribution.



## Model Building
### Baseline Model
A baseline model is established to set a benchmark for subsequent models. Mean Absolute Error (MAE) and Mean Squared Error (MSE) are calculated to evaluate its performance.

### Model Selection and Evaluation
Several models are trained and evaluated:
- **Linear Regression**
- **Random Forest Regressor**
  - Hyperparameter tuning is performed using `RandomizedSearchCV` to optimize the model.
- **XGBoost Regressor**

The performance of each model is assessed using cross-validation, and the results are analyzed to select the best performing model based on MSE and MAE.

### Feature Importance
Feature importance is evaluated to understand the influence of different variables on the prediction of Airbnb rental prices.

## Saving the Model
The final model is saved using `pickle` to ensure reproducibility and to allow for future deployment scenarios.

## Summary of Results
Key Findings

Peak Seasons: January and July have the highest occupancy rates, indicating peak seasons for Airbnb rentals in Seattle.

Price Fluctuations: Rental prices peak during the summer, particularly in July, when demand is highest.

Influential Factors: Key factors influencing rental prices include the number of accommodates, room type, reviews per month, host duration, security deposit, and availability.

Model Performance

Three models were built and evaluated to predict rental prices:

Baseline Model:

Mean Absolute Error (MAE): 51.92

Random Forest Regressor:

Mean Absolute Error (MAE): 29.82

XGBoost Regressor:

Mean Absolute Error (MAE): 30.01

The Random Forest and XGBoost models significantly improved prediction accuracy compared to the baseline model.


## Acknowledgments
Kaggle: For providing the Airbnb Seattle dataset.

Google Colab: For providing the platform to execute and analyze the data.
