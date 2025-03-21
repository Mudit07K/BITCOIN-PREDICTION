Bitcoin Price Prediction Using LSTM and Optuna Optimization

This project focuses on predicting Bitcoin (BTC) closing prices using machine learning techniques, particularly Long Short-Term Memory (LSTM) neural networks. It also implements Optuna for hyperparameter optimization to enhance model performance.
📊 Project Overview
Objective

    Analyze historical Bitcoin price data.
    Apply data preprocessing and feature scaling.
    Build an LSTM model to predict future BTC prices.
    Optimize model hyperparameters using Optuna.
    Evaluate the model's performance and visualize predictions.

📚 Dataset Information

    Dataset Name: BTC-USD.xls
    Columns:
        date - Date of the record.
        open, high, low, close - BTC price details.
        volume - Trading volume of BTC.
        RSI - Relative Strength Index (if available).

🧩 Key Project Stages
1. Data Preprocessing

    Loaded the dataset using pandas.
    Converted the date column to datetime format.
    Checked for missing values and handled them appropriately.
    Split the data into training, validation, and testing sets.
        Training Data: From the start to 8 months before the last record.
        Validation Data: 4 months before the test period.
        Test Data: Last 4 months of the dataset.

2. Feature Scaling

    Used MinMaxScaler to scale features (open, high, low, volume).
    Applied separate scaling to the target variable (close).

3. Sequence Creation

    Created time sequences using a look_back period of 30 days.
    Generated sequences for training, validation, and test sets.

🤖 Model Architecture
Base LSTM Model

    Two LSTM layers with 64 units each.
    Dense layer with 32 units and ReLU activation.
    Output Dense layer for predicting closing prices.

Optimized Model with Optuna

    Used Optuna to search for optimal:
        Number of LSTM units.
        Dropout rate.
        Choice of optimizers (Adam, AdamW, Nadam).
        Activation function (relu, leaky_relu, elu).

    Trained using EarlyStopping with patience of 20 epochs.

🎯 Model Evaluation

    Loss Metric: Mean Squared Error (MSE)
    Performance Metric: R² Score on test data
    Final R² Score achieved: ~0.97 (97.48% accuracy)

📈 Results and Visualization

    Plotted actual vs. predicted prices.
    Displayed training, test, and predicted results on a candlestick and line chart.
    Highlighted moving average trends and autocorrelation.

🔥 Future Price Prediction

    Predicted future BTC prices for the next 10 days.
    Generated a DataFrame with prediction dates and corresponding prices.

🛠️ Dependencies

    Python 3.x
    Key Libraries:
        pandas, numpy, matplotlib, seaborn
        scikit-learn, statsmodels
        tensorflow, keras, optuna
        mplfinance (for candlestick visualization)
