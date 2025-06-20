# FPT.VN Stock Price Analysis

## Overview
This project analyzes the historical stock price movements of **FPT Corporation (FPT.VN)**, a leading technology company listed on the Ho Chi Minh Stock Exchange (HOSE). The analysis covers the period from **June 1, 2023** to **May 30, 2025**, using daily stock price data. The objective is to identify trends, volatility, and potential investment opportunities through data cleaning, preprocessing, technical indicator calculations, and interpretation of results.

## Objectives
- **Data Collection**: Retrieve historical stock price data for FPT.VN using the vnstock library.
- **Data Cleaning**: Ensure the dataset is free of missing values, duplicates, and outliers.
- **Technical Analysis**: Calculate key technical indicators such as Simple Moving Average (SMA) and Exponential Moving Average (EMA) to identify trends.
- **Correlation Analysis**: Examine relationships between closing prices, SMAs, EMAs, and returns using a correlation matrix.
- **Investment Insights**: Provide actionable investment recommendations based on observed trends, volatility, and technical indicators.

## Dataset
The dataset contains daily stock price data for **FPT.VN** from **June 1, 2023** to **May 30, 2025**, retrieved using the **vnstock library**. It includes the following columns:
- **time**: Date of the trading session (datetime format).
- **open**: Opening price of the stock.
- **high**: Highest price during the trading session.
- **low**: Lowest price during the trading session.
- **close**: Closing price of the stock.
- **volume**: Trading volume for the day.
- **ticker**: Stock symbol (FPT).

The dataset is saved as **FPT_raw_data.csv** after initial collection.

## Methodology

### 1. Data Collection
Historical stock data is fetched using the **vnstock** library with the `stock_historical_data` function.  
Data is stored in a Pandas DataFrame and exported to a CSV file (**FPT_raw_data.csv**).

### 2. Data Cleaning and Preprocessing
- Convert the `time` column to datetime format.
- Check for and remove duplicates.
- Verify the absence of missing values.
- Detect outliers in the `close` column using the **Interquartile Range (IQR)** method. No outliers were found in the dataset.

### 3. Technical Indicators
- Calculate the **20-day Simple Moving Average (SMA_20)** and **50-day Simple Moving Average (SMA_50)** to identify short-term and long-term trends.
- Compute the **20-day Exponential Moving Average (EMA_20)** for a more responsive trend indicator.
- Calculate **daily returns** to assess price volatility.

### 4. Correlation Analysis
- Generate a **correlation matrix** to analyze relationships between `close`, `SMA_20`, `EMA_20`, and **Return**.
- Visualize the correlation matrix using a **heatmap** (seaborn).

### 5. Interpretation and Recommendations
- Identify key trends, such as long-term growth, periods of volatility, and consolidation phases.
- Provide investment strategies for both long-term and short-term investors, including buy/sell signals based on SMA/EMA crossovers and risk management techniques.

## Key Findings

- **Long-Term Uptrend**: FPT.VN exhibited steady growth from April 2024 to May 2024, with the closing price rising from ~100,000 to 115,510 VND, indicating strong market interest.
- **Adjustment Period**: A notable price drop in March 2025 (~130,000 to ~123,000 VND) suggests a market correction, possibly due to selling pressure or negative news.
- **Short-Term Stability**: Prices stabilized between January 2025 and March 2025 (~140,000–150,000 VND), indicating a consolidation phase.

### High Volatility Periods:
- **April–May 2024**: A 13% price increase signals strong positive sentiment.
- **March 2025**: An 8% drop highlights sensitivity to external factors.
- **October 2024**: A 5.7% rise reflects strong buying momentum.

## Investment Recommendations

- **Long-Term**: Buy at lower prices (~120,000–130,000 VND) and hold for 6–12 months, targeting 140,000–150,000 VND.
- **Short-Term**: Buy when the closing price exceeds SMA_20/EMA_20 and sell when it dips below.
- **Risk Management**: Set a stop-loss of 5–7% below the purchase price to mitigate volatility risks.

## Limitations

- The dataset only covers data up to **May 30, 2025**. For real-time analysis beyond this date, update the `end_date` in the `stock_historical_data` function to **2025-06** or later.
- The analysis does not include the **Relative Strength Index (RSI)** due to missing code in the provided notebook. Consider adding RSI for overbought/oversold signals.
- External factors (e.g., financial reports, market news) are not directly incorporated but are recommended for comprehensive analysis.

## KNN-Based Price Prediction (Optional Enhancement)
- To explore the predictive potential of machine learning in financial analysis, the K-Nearest Neighbors (KNN) algorithm was applied to forecast the next-day closing price of FPT.VN. The model used features such as current closing price, 20-day SMA, 20-day EMA, and calculated RSI (if available) to identify similar historical patterns and estimate future prices based on the average outcome of the closest neighbors.

- Although KNN is a relatively simple model, it provides a useful baseline and performs reasonably well for short-term predictions in stable market conditions. This implementation demonstrates the integration of information technology and machine learning into stock analysis, and lays the foundation for future adoption of more complex models.

## Future Improvements

- Add more technical indicators, such as **RSI**, **MACD**, or **Bollinger Bands**, to enhance trend and volatility analysis.
- Incorporate **fundamental analysis** (e.g., earnings reports, P/E ratio) to complement technical insights.
- Extend the dataset beyond May 30, 2025, for real-time monitoring and forecasting.
- Implement predictive models (e.g., **ARIMA**, **LSTM**) to forecast future price movements.

