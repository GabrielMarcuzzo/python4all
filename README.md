# python4all
Share Python scritps higly applicable to business management students.

# Compare stock prices from different companies listed in different stock exchanges
# retrived stock price data from yahoo finance

import numpy as np
import pandas as pd
from pandas_datareader import data as wb
import matplotlib.pyplot as plt

tickers = ["PETR4.SA", "VALE3.SA", "BMW.F", "LHA.F"]
stock_prices_br = pd.DataFrame()
for t in tickers:
	stock_prices_br[t] = wb.DataReader(t, data_source = "yahoo", start ="2020-1-1")["Adj Close"]

(stock_prices_br/ stock_prices_br.iloc[0] * 100).plot(figsize = (15, 6));
plt.show
