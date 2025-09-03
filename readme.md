# Intraday Trading Strategy

This repository contains a Jupyter Notebook (`twitter_strategy.ipynb`) that implements an intraday trading strategy based on daily predictions and intraday technical indicators. The strategy generates trading signals and calculates cumulative returns.

## Files

*   `twitter_strategy.ipynb`: The Jupyter Notebook containing the trading strategy implementation.
*   `sentiment_data.csv`: A CSV file containing sentiment data used in the daily prediction calculation (as indicated by the notebook's code, although the generation of `predictions` and `variance` is not fully shown).

## Strategy Overview

The strategy consists of the following steps:

1.  **Daily Prediction and Premium Calculation**: Calculates a "prediction premium" based on daily predictions and variance (details of how `predictions` and `variance` are generated are not fully included in the visible cells). A 6-month rolling standard deviation of the prediction premium is also calculated.
2.  **Daily Signal Generation**: A daily signal is generated based on whether the prediction premium is above or below its 6-month rolling standard deviation.
3.  **Merge with Intraday Data**: The daily signal is merged with intraday (5-minute) data.
4.  **Intraday Indicator Calculation**: Intraday technical indicators, specifically RSI and Bollinger Bands, are calculated on the intraday data.
5.  **Intraday Signal Generation**: An intraday signal is generated based on the RSI and Bollinger Bands.
6.  **Position Entry and Hold**: A position entry signal is determined by combining the daily and intraday signals. The position is held until the end of the day.
7.  **Strategy Return Calculation**: The daily returns of the strategy are calculated and then compounded to get the cumulative strategy returns.

## Requirements

To run this notebook, you will need:

*   Python 3.x
*   pandas
*   numpy
*   matplotlib
*   pandas\_ta

You can install the required libraries using pip:
