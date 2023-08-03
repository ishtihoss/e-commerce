# Project: E-commerce Sales Analysis and Quantity Prediction

This project involves analyzing an e-commerce dataset and building a model to predict the quantity of product sales. We focus our analysis on sales data from the United Kingdom. 

## Dataset
The dataset consists of e-commerce transactions from different countries. For each transaction, we have the following information:
- `InvoiceNo`: Invoice number
- `StockCode`: Product code
- `Description`: Product name
- `Quantity`: The quantity of each product per transaction
- `InvoiceDate`: The date and time of the transaction
- `UnitPrice`: Unit price of the product
- `CustomerID`: Customer identifier
- `Country`: The country where the customer resides

## Data Exploration and Visualization
We start by exploring the dataset, performing necessary preprocessing steps, and visualizing the data to gain insights. We:
- Convert `InvoiceDate` to datetime type and extract the date, time, and day of the week.
- Calculate the total revenue for each transaction.
- Visualize the total revenue for the top 10 countries by day of the week.
- Visualize the total revenue for each country per year.
- Explore the mean hourly revenue by day of the week, both globally and for the UK.

## Feature Engineering
We focus on data from the UK and perform the following steps:
- Convert `DayOfWeek` to a numerical representation.
- Winsorize the `Quantity` column to limit the effect of extreme values.
- Generate lag features and moving average features based on the `Quantity` column.

## Model Building and Evaluation
We split the data into a training set (before a certain cutoff date) and a test set (after the cutoff date). We drop irrelevant columns and prepare the data for model training.

We train an XGBoost model on the training data and evaluate its performance on the test data using the root mean square error (RMSE). We also conduct hyperparameter tuning using grid search and k-fold cross-validation to find the best hyperparameters for the model.

## Usage
To run the analysis, you need to have Python and the necessary libraries installed. You can then clone this repository and run the Python script.

## Libraries Used
- pandas
- numpy
- matplotlib
- seaborn
- xgboost
- scipy
- sklearn

## License
This project is licensed under the MIT License.