# Alberta Oil Sands Production vs Global Oil Prices

## Project Overview:

The idea of this project was to see if global oil prices have a direct impact on Alberta oil sands production. In particular, the analysis focuses on Alberta's on-conventional oil production,
which is predominantly oil-sands products, such as bitumen and synthetic crude.

The goal was to see whether oil sands production has the same short-term response to global oil prices as is typical in oil markets.

## Data Sources:
#### 1. WTI Crude Oil Prices
- Source: Federal Reserve Economic Data (FRED) https://fred.stlouisfed.org/series/DCOILWTICO
- Data includes the WTI oil price for every single day since 1986

#### 2. Alberta Oil Production Data
- Source: Government of Alberta Economic Dashboard https://economicdashboard.alberta.ca/dashboard/oil-production/
- Data include non-conventional oil production (mostly oil sands) and conventional oil products(non-oil sands), and monthly dates since 2007
- Production is in millions of cubic meters(m^3)


## Data Cleaning and Preparation
The project involved several preprocessing steps:

#### 1. WTI Data
- Converted date columns into datetime format
- Renamed columns for readability
- Filled missing values using forward fill -
- Converted daily prices into monthly average prices
#### 2. Alberta Production Data
- Renamed columns to match WTI data
- Removed the unnecessary column named "label"
- Pivoted the dataset so conventional and non-conventional production appeared side-by-side and not all in one column
#### Merging
The two datasets were merged using their monthly date columns.
- Date | WTI Price | Conventional Oil | Non-conventional Oil

## Exploratory Analysis
Several visualizations were created:

#### 1. WTI Oil Prices Over Time'
Shows the volatility of global oil prices, including:
- 2008 oil price spike
- 2014 oil collapse
- 2020 COVID crash
- 2022 energy price spike
#### 2. Alberta Oil Sands Production Over Time
- Non-conventional (oil sands) production shows a strong long-term upward trend.
- Production generally increased even during periods of major oil price declines.

#### 3. Dual-Axis Plot
Compared WTI prices and oil sands production
- Oil sands production does not closely track short-term oil price shocks.
<img width="1076" height="449" alt="image" src="https://github.com/user-attachments/assets/7801391f-3c73-499d-910f-74343265097e" />

## Correlation Analysis
Tested the correlation between WTI prices and oil sands production
#### 1. Raw correlation
- Between WTI prices and oil sands production
#### Result
```
Approximately -0.28662
```
- I deemed this result misleading since the gap between early oil sands production and price was extremely different

#### 2. Differenced correlation
To reduce trend effects, month-to-month changes were analyzed:
- Analyzed the same data as before
#### Result
```
Approximately 0.181465
```
- Suggested a weak positive relationship, but still has the same issues as before

#### 3. Lagged Analysis
- 6-month and 12-month periods were compared against future production changes.
#### Result
```
6 months ~= -0.0087071
12 month2 ~= 0.0218487
```
- Basically, no correlation between production and prices 

## Key Findings
Firstly, the correlation is difficult. Oil sands production is very susceptible to extreme weather, which can drastically reduce production. Another issue is that I cannot see exactly when this extreme weather event occur
or when a refinery is damaged, or some other thing that could cause production to increase/decrease
- Hence why I did various types of correlation. The dual-axis graph very clearly states the oil sands production increase despite oil prices (with some frequent dips, which I ASSUME is weather)

Now, on to the important and meaningful findings:
- Oil sands production is largely insensitive to short-term oil price shocks
- Production follows a strong, long-term upward trend
- Long-term investment and infrastructure expansion appear more important than short-term market prices
- Correlations between price and production levels can be misleading due to underlying time trends

## The big question
Modern thinking says that if the price of something goes down, you should generally cut back production to maintain a certain level of profit and keep your business. So, how do oil sands companies weather the storm of frequent oil fluctuation and regulatory burdens? How does Alberta compete with other countries such as Brazil, Guyana, Venezuela, all of the Middle East, and Russia(pre-war)?
- From my understanding, stability, and access to the second-largest market (and more recently, with the Trans Mountain pipeline, the largest market)

