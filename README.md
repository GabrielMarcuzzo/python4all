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

# Plotar um gráfico de barras

import matplotlib.pyplot as plt

x1 = [1, 3, 5, 7, 9]
y1 = [2, 3, 7, 1, 0]

x2 = [2, 4, 6, 8, 10]
y2 = [5, 1, 3, 7, 4]


titulo = "Gráfico de barras criado com Python"
eixox = "Eixo X"
eixoy = "Eixo Y"

plt.title(titulo)
plt.xlabel(eixox)
plt.ylabel(eixoy)

plt.bar(x1, y1, label = "Grupo 1")
plt.bar(x2, y2, label = "Grupo 2")
plt.legend()

plt.show()

