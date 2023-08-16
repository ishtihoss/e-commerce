# Project: E-commerce Sales Analysis and Quantity Prediction

In this project, we build a machine learning model to predict the quantity of products sold in an e-commerce store based on historical sales data. We use the XGBoost regressor, a powerful gradient boosting framework, to create our predictive model. 

The dataset used for this project is a comprehensive record of transactions from an online retail store. It contains details such as invoice number, stock code, product description, quantity sold, invoice date, unit price, customer ID, and country of purchase.

The project begins with data loading, where we ingest the data from a CSV file and perform an initial examination of the data structure, including a statistical summary of numerical and categorical columns. 

Next, we enrich the dataset by extracting new features from the 'InvoiceDate' column, including the date, time, and day of the week of each transaction. We also create a 'Revenue' column by multiplying the quantity of products sold by their unit price. We then analyze sales trends by visualizing the total revenue by country and day of the week, and the total revenue from each country per year.

For our predictive model, we focus on transactions from the United Kingdom, as this country has the most transactions in the dataset. We transform the 'Quantity' column with winsorization to limit the effect of extreme values. 

We engineer additional features based on the quantity of products sold. These features include the quantity sold in the past few days (lag features) and the moving average quantity sold over the past few days. 

After preparing our features, we split the data into a training set and a testing set, with the test set comprising the most recent 3 months of data. We then train our XGBoost model on the training set and evaluate its performance on the test set using the root mean square error (RMSE) metric.

Finally, we perform hyperparameter tuning on our XGBoost model using grid search and k-fold cross-validation to find the best parameters that minimize our RMSE.


## The outcome of this project is a machine learning model that can predict the quantity of products sold on a given day, which can be helpful for managing inventory and forecasting revenue. 

The outcome of this project is a machine learning model that can predict the quantity of products sold on a given day, which can be helpful for managing inventory and forecasting revenue.

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
