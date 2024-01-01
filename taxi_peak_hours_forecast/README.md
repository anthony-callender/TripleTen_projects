# Sweet Lift Taxi Company - Predicting Taxi Orders

## Project Description

Sweet Lift Taxi Company aims to improve driver allocation during peak hours by predicting the volume of taxi orders for the next hour. The goal is to build a predictive model with an RMSE metric on the test set not exceeding 48.

## Project Instructions

1. **Data Collection and Preprocessing**
   - Download the data stored in `taxi.csv`.
   - Resample the data by one hour for analysis.

2. **Analysis**
   - Analyze the data for insights into the taxi order trends.
   - Visualize the distribution of orders on daily and hourly timeframes.
   - Generate features like lagged values and rolling means to enhance modeling.

3. **Model Training and Testing**
   - Train different models using the prepared features and experiment with various hyperparameters.
   - Evaluate models using cross-validation techniques.
   - Test the models on a 10% holdout test set.

4. **Final Conclusion**
   - Summarize the best-performing model and its hyperparameters.
   - Reflect on the importance of feature engineering and hyperparameter tuning in model performance.

## Data Description

- The dataset contains a single column, 'num_orders,' representing the count of taxi orders.
- Initial data spans from March 1, 2018, to August 31, 2018, in hourly intervals.

## Code Preparation

The project code includes:
- Data import and preprocessing using Python libraries like Pandas and NumPy.
- Exploratory Data Analysis (EDA) utilizing Matplotlib, Seaborn for visualizations.
- Feature engineering to create lagged values and rolling means.
- Model training and evaluation using Linear Regression, Random Forest, LightGBM, and XGBoost.

## Analysis Summary

### Daily Analysis
- Observing a positive skew in the daily order distribution, indicating a healthy increase in orders over time.
- Visualization shows a consistent increase in orders throughout the year.

![taxi_sweet_lift](https://github.com/anthony-callender/TripleTen_projects/assets/129457454/a2794fc8-a9a6-4a36-ada4-f46570cedf23)


### Hourly Analysis
- Average hourly orders: 84.
- Positive peaks (outliers) correlated with weekends/holidays, indicating increased travel.
- Lack of significant negative outliers signifies good financial health for the company.

## Model Evaluation

- Linear Regression: Average RMSE on training set - 31.45
- Random Forest: Average RMSE on training set - 28.51
- LightGBM: Average RMSE on training set - 28.16 (Best Performing)
- XGBoost: Average RMSE on training set - 29.42

## Hyperparameter Tuning

- Conducted RandomizedSearchCV for LightGBM to optimize hyperparameters.
- Achieved best RMSE on the test set: 48.15

## Final Model

- Fine-tuned LightGBM model:
  - num_leaves: 90
  - n_estimators: 310
  - min_child_samples: 25
  - max_depth: 6
  - learning_rate: 0.3
- Final RMSE on the test set: 46.31

## Conclusion

Through systematic model evaluation, it's clear that the LightGBM model, coupled with specific feature engineering and hyperparameter optimization, best predicts taxi orders. This process emphasized the importance of parameter tuning and feature selection in achieving a predictive RMSE below 48.
