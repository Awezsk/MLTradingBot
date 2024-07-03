# ML-Based Trading Strategy with FinBERT Sentiment Analysis

This project implements a machine learning-based trading strategy using the Lumibot framework and FinBERT for sentiment analysis of financial news. The strategy makes trading decisions based on the sentiment of recent news headlines related to a specific stock symbol.

## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
3. [Project Structure](#project-structure)
4. [How It Works](#how-it-works)
5. [Usage](#usage)
6. [Customization](#customization)
7. [Disclaimer](#disclaimer)

## Prerequisites

- Python 3.7+
- An Alpaca trading account (paper trading is fine)

## Installation

1. Clone this repository:
2. Install the required packages: pip install lumibot alpaca-trade-api pandas transformers torch
3. 3. Set up your Alpaca API credentials in the code or use environment variables.

## Project Structure

- `ml_trader.py`: The main script containing the MLTrader strategy and backtesting setup.
- `README.md`: This file, containing project documentation.

## How It Works

1. **Data Collection**: The strategy fetches recent news headlines for a specified stock symbol using the Alpaca API.

2. **Sentiment Analysis**: The FinBERT model analyzes the sentiment of these headlines, classifying them as positive, negative, or neutral.

3. **Trading Decisions**: Based on the sentiment analysis:
- If the sentiment is strongly positive, the strategy buys the stock.
- If the sentiment is strongly negative, the strategy sells the stock.

4. **Position Sizing**: The strategy calculates the number of shares to trade based on a specified cash-at-risk parameter.

5. **Backtesting**: The strategy is backtested using historical data from Yahoo Finance.

## Usage

1. Update the `API_KEY`, `API_SECRET`, and `BASE_URL` variables with your Alpaca credentials.

2. Run the script: python ml_trader.py
3. The script will execute a backtest of the strategy and output the results.

## Customization

- Adjust the `cash_at_risk` parameter in the strategy initialization to control the position size.
- Modify the `symbol` parameter to trade different stocks.
- Change the `start_date` and `end_date` to backtest over different time periods.
- Adjust the sentiment probability threshold (currently set at 0.999) in the `on_trading_iteration` method.

## Disclaimer

This project is for educational purposes only. It is not financial advice, and should not be used for actual trading without thorough testing and risk management. Trading involves significant risk of loss.
