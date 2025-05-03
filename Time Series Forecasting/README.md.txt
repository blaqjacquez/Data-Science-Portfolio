# SALES FORECASTIN USIN LSTM NEURAL NETWORKS
## Project Description
This project presents a deep learning-based solution to forecast product sales using a Long Short-Term Memory (LSTM) neural network. It is built on historical sales data from the Global Superstore dataset and demonstrates how machine learning can outperform traditional methods by learning time-based patterns and trends.

## Problem Statement
Retailers often face challenges when predicting product demand due to seasonal trends, market shifts, and unpredictable consumer behavior. Traditional forecasting models fail to capture long-term dependencies, resulting in inefficient inventory management and missed revenue opportunities.

## Solution Overview
We implemented an LSTM model to forecast sales using a cleaned and preprocessed version of the Global Superstore dataset. The solution pipeline involves:

- Ingesting sales data from Azure Blob Storage
- Preprocessing the data for time series modeling
- Reshaping and feeding the data into an LSTM model
- Evaluating prediction performance using RMSE and MAE
- Visualizing actual vs. predicted values


## Tools & Technologies
- Python
- TensorFlow / Keras for deep learning
- Pandas, NumPy for data manipulation
- Azure Blob Storage SDK for cloud data ingestion
- Scikit-learn for evaluation metrics
- Matplotlib / Seaborn for visualization

## Dataset
Global Superstore Sales Dataset from Kaggle (https://www.kaggle.com/datasets/apoorvaappz/global-super-store-dataset?resource=download).

## Methodology

### 1. Data Ingestion
Used Azure Blob Storage to simulate a cloud pipeline. The dataset was loaded using `azure.storage.blob` and `pandas`.

### 2. Data Preprocessing
- Removed null values
- Aggregated sales by day
- Normalized data to prepare for deep learning
- Structured data into supervised format (sliding window approach)

### 3. Model Architecture
Implemented using TensorFlow/Keras:
- 1 LSTM layer with return sequences
- Dropout for regularization
- Dense layer for output

### 4. Training & Testing
- Split dataset chronologically (80/20 split)
- Trained model using `fit()` on training set
- Predicted on test set and evaluated using:
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)

### 5. Visualization
- Actual vs Predicted sales curves
- Sales trends and error metrics plotted using matplotlib/seaborn

## What isLSTM and Why?
Long Short-Term Memory (LSTM) network is a type of Recurrent Neural Network (RNN) specifically designed to learn long-term dependencies in sequential data. Unlike traditional models (e.g. ARIMA, linear regression), LSTMs are well-suited for time series with long-term dependencies. Their internal memory state allows them to learn complex temporal relationships, capturing seasonality and trend shifts in sales data.

## Results
- Forecasts showed strong alignment with actual sales patterns
- LSTM outperformed linear regression baseline
- RMSE and MAE indicated low error, demonstrating high predictive power

## Business Impact
- Enables smarter inventory planning and supply chain optimization
- Reduces stockouts and overstock scenarios
- Improves revenue predictability and customer satisfaction
- Establishes foundation for future dynamic pricing and demand forecasting system



## How to Run
1. Clone the repository
2. Install dependencies using `pip install -r requirements.txt`
3. Set up Azure Blob Storage credentials (if you decide to use Azure)
4. Run the notebook or convert to script for deployment


## Author

Michael Otu
Data Scientist | Finance & AI Enthusiast
[LinkedIn](https://www.linkedin.com/in/michaelotu/) | [Email](mcotu08@gmail.com)


