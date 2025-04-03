# 20-Day Average Daily Return Rank

# Category:
Price Momentum

# Color:
Green

# Tags:
daily return, 20-day average, cross-sectional rank, price momentum

# Description:
This alpha calculates the average daily return over the past 20 days and ranks stocks based on
this metric. By computing the difference between the current closing price and the previous day's
closing price, normalizing by the previous day's closing price, and averaging this daily return 
over a 20-day window, the alpha identifies stocks with consistent performance trends. The final 
ranking highlights stocks with higher average daily returns over the specified period, aiming to
capture momentum in stock prices.

# Code
```fastexpression
rank(ts_mean((close - ts_delay(close, 1)) / ts_delay(close, 1), 20))
```
