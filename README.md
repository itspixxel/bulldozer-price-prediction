# 🚜 Bulldozer Price Prediction

This project is an end-to-end Machine Learning regression task aimed at predicting the sale price of bulldozers based on historical data. The dataset and problem are sourced from the **Kaggle Bluebook for Bulldozers** competition.

## 📌 Project Overview

The goal of this project is to build a machine learning model that can predict the future sale price of a bulldozer, given its characteristics and previous examples of how much similar bulldozers have been sold for.

### 1. Problem Definition

> How well can we predict the future sale price of a bulldozer, given its characteristics and previous examples of how much similar bulldozers have been sold for?

### 2. Data

The data is downloaded from the Kaggle Bluebook for Bulldozers competition:

* **Train.csv**: The training set, containing data through the end of 2011.
* **Valid.csv**: The validation set, containing data from January 1, 2012 – April 30, 2012.
* **Test.csv**: The test set, containing data from May 1, 2012 – November 2012.

### 3. Evaluation

The evaluation metric for this competition is the **RMSLE (Root Mean Squared Log Error)** between the actual and predicted auction prices. The goal is to build a model that minimizes this error.

---

## 🛠️ Tools & Technologies

The project uses the following Python libraries:

* **Data Manipulation**: `pandas`, `numpy`
* **Visualization**: `matplotlib`
* **Machine Learning**: `scikit-learn`
* `RandomForestRegressor`
* `RandomizedSearchCV`
* Evaluation Metrics: `mean_squared_log_error`, `mean_absolute_error`, `r2_score`



---

## 🚀 Project Workflow

### 1. Data Preprocessing & EDA

* **Parsing Dates**: Converting date strings into `datetime` objects to enrich time-series data.
* **Sorting**: Sorting the DataFrame by `saledate` as it's a time-series problem.
* **Feature Engineering**: Extracting year, month, day, and day-of-week parameters from the `saledate` column.

### 2. Handling Missing Data & Encoding

* **Categorical Encoding**: Converting string columns into categories and then numerical values.
* **Missing Values**:
* Filling numerical missing values with the median.
* Converting categorical variables into numbers and adding a binary column to indicate if the value was originally missing.



### 3. Modelling

* **Initial Model**: Training a baseline `RandomForestRegressor`.
* **Hyperparameter Tuning**: Using `RandomizedSearchCV` to find the best settings for the model on a subset of the data to save time.
* **Evaluation**: Implementing a custom evaluation function to calculate RMSLE, MAE, and $R^2$.

### 4. Feature Importance

Analyzing which bulldozer characteristics (e.g., `YearMade`, `ProductSize`, `fiSecondaryDesc`) contributed most to the model's price predictions.

---

## 📊 Results & Conclusion

The final model is evaluated on the validation set. By tuning hyperparameters and performing feature engineering, the model achieves a competitive RMSLE score, demonstrating the effectiveness of Random Forest for structured tabular data.

### How to use this repository:

1. Clone the repository.
2. Install dependencies: `pip install pandas numpy matplotlib scikit-learn`.
3. Open the `end-to-end-bulldozer-price-prediction.ipynb` notebook and run the cells.