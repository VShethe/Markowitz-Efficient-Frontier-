
# Markowitz Efficient Frontier





## Table of Content


**1. NSE - Markowitz Efficient Frontier**
 - Markowitz Efficient Frontier - SETFNN50, INFY
 - Calculating Beta of Stocks

**2. USA Stocks -  Markowitz Efficient Frontier**
 - Markowitz Efficient Frontier - SETFNN50, INFY
 - Markowitz Efficient Frontier  - PG, MSFT, BP
 
## Normalization of Data:
![image](https://user-images.githubusercontent.com/128286364/230934899-7d254831-04e7-4568-b31a-8f53f820ab97.png)
![image](https://user-images.githubusercontent.com/128286364/230935027-db573d90-f1b0-41b1-ac8e-597e304556d5.png)


## Project Description

1. **Markowitz Efficient Frontier**
Markowitz Efficient Frontier seeks to maximize the expected return of a portfolio for a given level of risk. It does this by constructing a set of portfolios that represent the optimal tradeoff between risk and return.

```bash
Create a loop with 1,000 iterations that will generate random weights, summing to 1, and will append the obtained values for the portfolio returns and the portfolio volatilities:

portfolio_returns = []
portfolo_volatilities = []

for x in range (1000):
    weights = np.random.random(2)
    weights /= np.sum(weights)
    portfolio_returns.append(np.sum(weights * log_returns.mean()))
    portfolo_volatilities.append(np.sqrt(np.dot(weights.T,np.dot(log_returns.cov() weights))))

```

```bash
Create a dictionary, called portfolios, whose keys are the strings “Return” and “Volatility”:

portfolio = pd.DataFrame({'Return':portfolio_returns, 'Volitality':portfolo_volatilities})

```

**Markowitz Efficient Frontier Graph**:
![image](https://user-images.githubusercontent.com/128286364/230936040-f4837015-20e3-4c34-9972-288d95d9a2c1.png)


## Installation

To install iexfinance:

url: <https://pypi.org/project/iexfinance/>

url: <https://iexcloud.io/>
```bash
pip install iexfinance
```
To install NSEpy:

url: <https://nsepy.xyz/>
```bash
pip install nsepy
```
## Deployment

To deploy this project run

```bash
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plt
  from datetime import datetime
  from pandas_datareader import data as wb
```

```bash
  from iexfinance.stocks import Stock, get_historical_data

  start = datetime(2018, 1, 1)
  end = datetime(2023, 3, 23)

  api_key = 'API_KEY'
```

Creating a portfolio:
```bash
tickers = ['Stocks']
mydata = pd.DataFrame()
for t in tickers:
    mydata[t] = get_historical_data(t, start, end, output_format = 'pandas', token=api_key)['close']
```
