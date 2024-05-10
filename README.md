# Airbnb Price Prediction for Seattle

## Project Overview
This project aims to analyze Airbnb rental prices in Seattle to uncover insights on demand fluctuations and occupancy rates. The analysis focuses on determining peak seasons, price variability, and average occupancy rates, helping stakeholders optimize pricing and improve rental strategies.

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

## Data Source
The data used in this project is sourced from the publicly available Airbnb dataset for Seattle, covering calendar years and listing details.

## Libraries Used
Pandas, NumPy for data manipulation.
Matplotlib, Seaborn for data visualization.
Scikit-Learn for machine learning and predictive modeling.
NLTK for natural language processing tasks.

## Data Preprocessing
### Encoding and Imputing
- **Encoding**: Categorical variables such as `cancellation_policy`, `property_type`, `room_type`, and `bed_type` are encoded using one-hot encoding to convert them into a format suitable for modeling.
- **Imputing**:
  - Numerical attributes are imputed using the median to handle outliers.
  - Categorical attributes are imputed with the most frequent category to maintain the distribution.

### Handling Missing Data
Missing values are imputed using the mean for numerical columns and the most frequent category for categorical columns to ensure the dataset is suitable for predictive modeling.

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

## Usage Example
Here's how to load and use the final model to make predictions:
```python
import pickle

# Load the model from disk
with open('seattle_airbnb.pickle', 'rb') as model_file:
    model = pickle.load(model_file)

# Assume X_test is preloaded with the features of the listings for which you want to predict prices
predictions = model.predict(X_test)
print(f"Predicted rental prices: {predictions}")

## Installation and Usage
Ensure you have Python installed on your system.
