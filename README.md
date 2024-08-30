# TimeSeriesAnalysis

# Project Title: Analyzing and Forecasting MercadoLibre's Search Traffic and Stock Patterns

## Project Objective:
As a Growth Analyst at MercadoLibre, the most popular e-commerce platform in Latin America, your task is to analyze the company's financial and user data in innovative ways to assist in its growth. Specifically, you'll explore whether predicting search traffic can translate into successful stock trading strategies.

## What You’re Creating:
In this project, you'll develop a Jupyter notebook that documents your data preparation, analysis, and visualizations for all relevant time series data. The key components of this notebook will include:

- **Visualizations of Seasonality**: Display how seasonality, as measured by Google Search traffic, impacts the company.
- **Stock Price Correlation Analysis**: Evaluate the relationship between MercadoLibre's stock price and its Google Search traffic.
- **Prophet Forecast Model**: Develop a forecast model using Prophet to predict hourly user search traffic.


## Project Workflow:

### Step 1: Find Unusual Patterns in Hourly Google Search Traffic
To investigate if there's a link between Google Search traffic and any significant financial events at MercadoLibre, you'll search for unusual patterns in the data. Follow these steps:

1. **Data Import**:
   - Read the search traffic data into a pandas DataFrame.
   - Slice the data to focus on May 2020, the month during which MercadoLibre released its quarterly financial results.
   
2. **Data Visualization**:
   - Use `hvPlot` to visualize the search traffic for May 2020.
   - Identify any unusual patterns during this period.

3. **Traffic Analysis**:
   - Calculate the total search traffic for May 2020.
   - Compare this value to the monthly median across all months to determine if search traffic increased during the financial results release.

### Step 2: Mine the Search Traffic Data for Seasonality
To enhance marketing strategies, the marketing team wants to mine the search traffic data for seasonal patterns. Your goal is to identify predictable seasonal variations in user interest. Complete the following steps:

1. **Hourly Traffic Analysis**:
   - Group the hourly search data by day of the week (e.g., Monday vs. Friday).
   - Visualize the data using a heatmap with `hvPlot`, with the x-axis representing `index.hour` and the y-axis representing `index.dayofweek`.

2. **Weekly Traffic Analysis**:
   - Group the search data by week of the year to observe trends, particularly during the winter holiday period (Weeks 40 through 52).

### Step 3: Relate the Search Traffic to Stock Price Patterns
After mentioning your work on search traffic data to the finance team, they express interest in understanding if there's a relationship between search traffic and the company's stock price. You'll explore this by completing the following:

1. **Data Merging**:
   - Read and plot the stock price data.
   - Concatenate the stock price data with the search traffic data into a single DataFrame.

2. **Time Series Analysis**:
   - Slice the data to focus on the first half of 2020 (January to June).
   - Use `hvPlot` to visualize both time series and check for a common trend consistent with the narrative that e-commerce platforms gained new customers and revenue post initial market disruptions.

3. **Lagged Search Trends**:
   - Create a new column named `Lagged Search Trends` that shifts the search traffic by one hour.
   - Create additional columns for `Stock Volatility` (using an exponentially weighted four-hour rolling average) and `Hourly Stock Return` (percentage change in stock price on an hourly basis).

4. **Correlation Review**:
   - Review the time series correlation to answer whether a predictable relationship exists between lagged search traffic and stock volatility or between lagged search traffic and stock returns.

### Step 4: Create a Time Series Model Using Prophet
To forecast future trends in the hourly search data, you'll develop a time series model using Prophet. Follow these steps:

1. **Model Setup**:
   - Prepare the Google Search data for use in a Prophet forecasting model.

2. **Forecasting**:
   - Estimate the model and plot the forecast to evaluate the near-term popularity of MercadoLibre.

3. **Component Analysis**:
   - Plot the individual time series components of the model to answer key questions:
     - What time of day is the most popular?
     - Which day of the week sees the highest search traffic?
     - When is the lowest point for search traffic within the calendar year?
