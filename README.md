# Tesla Stock Price Prediction with LSTM

A machine learning project to predict Tesla (TSLA) stock prices using a Long Short-Term Memory (LSTM) neural network. This project fetches historical stock data from Yahoo Finance, processes it into a windowed dataset, trains an LSTM model, and implements recursive multi-step predictions.

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Usage](#usage)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Future Work](#future-work)
- [Disclaimer](#disclaimer)

## Overview

This project leverages historical TSLA stock price data to forecast future prices. By employing an LSTM network, the model is designed to capture temporal dependencies within the data. It focuses on recursive predictions where the model’s forecasts are iteratively used as inputs for subsequent predictions.

The data considered in this project spans from **January 1, 2020, to the present date**. The dataset is split as follows:

- **80% for training**
- **10% for validation**
- **10% for testing**

## Requirements

- **Python 3.7+**
- [yfinance](https://pypi.org/project/yfinance/)
- [pandas](https://pandas.pydata.org/)
- [numpy](https://numpy.org/)
- [matplotlib](https://matplotlib.org/)
- [tensorflow](https://www.tensorflow.org/)

You can install the required libraries with:

```bash
pip install yfinance pandas numpy matplotlib seaborn tensorflow
```

## Usage

1. **Data Download & Processing:**\
   The script downloads historical TSLA stock data starting from a specified date until today, resets the date index, and creates a windowed dataset for time-series modeling.

2. **Model Training:**\
   The LSTM model is trained on a dataset split into training, validation, and testing sets. Adjust the window size and training parameters as needed.

3. **Recursive Prediction:**\
   After training, the model is used for recursive forecasting, where its own predictions are used as inputs for generating future predictions.

To run the project, execute:

```bash
python main.py
```

Ensure that the file structure and script names match those in the repository.

## Model Architecture

The LSTM model used in this project consists of:

- **Input Layer:**\
  Accepts a window of historical closing prices (with shape corresponding to the window size and features).

- **LSTM Layer:**\
  Contains 64 units to capture temporal dependencies.

- **Dense Layers:**\
  Two hidden layers with 32 units each using ReLU activation to further process the extracted features.

- **Output Layer:**\
  A single neuron that outputs the predicted stock price.

## Results

The project produces several visualizations:

- **Training Predictions vs. Observations:**\
  ![image](https://github.com/user-attachments/assets/28c20050-bb02-4c27-8532-441023a546ac)


- **Validation Predictions vs. Observations:**\
  ![image](https://github.com/user-attachments/assets/a3872a6d-7640-49c7-b27d-b44e0d9d1f16)


- **Testing Predictions vs. Observations:**\
  ![image](https://github.com/user-attachments/assets/ee4a74e6-8d51-47db-9c76-ce2146f5068f)


- **Recursive Forecasts:**\
  ![image](https://github.com/user-attachments/assets/6a86756c-00ca-46d5-9baa-5eb836cc534d)

- **Next Day Prediction:**\
  ![image](https://github.com/user-attachments/assets/edc39415-029f-4955-96bc-63d99c5b72cb)



## Future Work

- **Enhanced Forecasting:**\
  Experiment with different window sizes, additional features (e.g., trading volume, technical indicators), and alternative LSTM configurations.

- **Error Mitigation:**\
  Explore techniques like scheduled sampling to reduce error accumulation during recursive predictions.

- **Multi-step Forecasting:**\
  Develop models that directly forecast multiple future steps to improve long-term prediction stability.

- **Model Optimization:**\
  Fine-tune hyperparameters and incorporate regularization techniques to further improve generalization and robustness.

## Disclaimer

This project is intended as an educational and experimental implementation for predicting stock prices. The predicted changes or prices are not guaranteed to be 100% accurate and should not be relied upon for making financial decisions. This model can offer a general idea of price movements and serves as a foundation for further development towards long-term forecasting improvements.

