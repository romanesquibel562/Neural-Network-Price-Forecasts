# Neural-Network-Price-Forecasts
This project implements a deep learning pipeline to forecast NVIDIA (NVDA) stock prices using historical hourly closing data via a multi-layer Long Short-Term Memory (LSTM) neural network built in PyTorch. The model is trained to recognize temporal patterns in market behavior and make continuous, live predictions of future price movements.

Unlike static models, this system is designed for real-time operation, updating itself every 10 minutes by fetching the most recent stock prices from Yahoo Finance (yFinance), processing the input sequence, and outputting a forecast. Results are visualized dynamically in a live-updating plot, making this suitable for integration into automated trading pipelines, monitoring tools, or as a research prototype for financial market modeling.

## Project Overview

The system retrieves NVDA stock data from Yahoo Finance, preprocesses it into supervised sequences, trains an LSTM model, and generates predictions for the next stock price value. A live prediction loop runs every 10 minutes, updating the model’s forecast in real time and displaying it through a continuously updating plot.

The LSTM model uses the previous 60 hourly closing prices to predict the next one. The model is trained locally and reused to serve real-time forecasts.

---

## Features

- Data ingestion from Yahoo Finance (hourly resolution)
- Sequence generation with MinMax normalization
- Multi-layer LSTM with:
  - 3 layers
  - 128 hidden units
  - Fully connected output
- Real-time prediction loop:
  - Fetches most recent data
  - Predicts the next closing price every 10 minutes
- Interactive Matplotlib plot that updates continuously
- Model evaluation using RMSE and MAE
- Background threading for concurrent data handling and plotting

---

## Install Instructions (Bash)
pip install -r requirements.txt

## Run the Model (Bash)
python lstm_stock_prediction.py


## Enable Real-Time Predictions

To enable real-time predictions go to the nn code and scroll to the last line of code, there you will uncomment the loop:

# threading.Thread(target=real_time_prediction_loop, daemon=True).start()
# update_real_time_plot()

once this line is uncommented, the model will run and fetch real-time data in 10 minute intervals.


## Evaluation metrics
Root Mean Squared Error (RMSE)

Mean Absolute Error (MAE)

Visual comparison of predicted vs actual prices

## Use cases
Multi-stock support (dynamic tickers)

Model persistence with continuous retraining

Integration with sentiment analysis for news-informed forecasting

Deployment using Streamlit or Flask for interactive dashboards

## Author 
Roman Esquibel

Data Analyst | Financial Modeler | Machine Learning Practitioner
LinkedIn: https://www.linkedin.com/in/roman-esquibel-75b994223/

