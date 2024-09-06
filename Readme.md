#By zeuxi141

This project is python code uses Dash, Plotly, and Keras to create an interactive cryptocurrency price analysis dashboard. It displays actual and predicted cryptocurrency closing prices using LSTM models and allows users to explore historical price highs, lows, and market volumes for multiple cryptocurrencies.


Stock price prediction BTC-USD, ETH-USD, ADA-USD

1. Libraries and Modules:
Dash: Used for creating the web application with interactive components.
dash_core_components (dcc) and dash_html_components (html): Provide HTML elements and graphs.
plotly.graph_objs: Used for creating interactive plots.
Keras: Loads the pre-trained LSTM model to predict cryptocurrency prices.
yfinance: Fetches historical cryptocurrency data.
sklearn.preprocessing.MinMaxScaler: Scales the data before using it in the model.
Numpy: Used for array manipulations.

2. Fetching Cryptocurrency Data:
A list of cryptocurrency symbols is defined, including popular coins like BTC, ETH, BNB, etc.
Historical data from Yahoo Finance is fetched for each cryptocurrency using yfinance.download(), starting from 2020 to the end of 2024.

4. Data Preprocessing:
The data is sorted by date, and only the closing prices are used for training the LSTM model.
80% of the data is used for training, and 20% is for validation.
The data is scaled using MinMaxScaler to normalize it between 0 and 1.

4. Loading the LSTM Model:
A pre-trained LSTM model is loaded using load_model("saved_model.h5").
The model predicts cryptocurrency closing prices based on the last 60 days of data. The predicted results are transformed back to their original scale using scaler.inverse_transform().

5. Creating the Dashboard Layout:
The dashboard consists of:

A title: "Cryptocurrency Price Analysis Dashboard".
Tabs to switch between different views:
BTC-USD Data: Displays the actual closing prices and LSTM-predicted prices.
Cryptocurrency Data: Allows users to select different cryptocurrencies from a dropdown to view their high vs low prices and market volume.
