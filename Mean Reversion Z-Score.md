# Mean Reversion Z-Score

# Category:
Price Reversion

# Color:
Red

# Tags:
z-score, mean reversion, 20-day moving average, standard deviation

# Description:
This alpha identifies potential mean reversion opportunities by calculating the
Z-score of the difference between the closing price and its 20-day moving average.
The Z-score measures how many standard deviations the current price is from the mean, 
indicating whether the asset is overbought or oversold. By multiplying the Z-score by 
-1, the signal is inverted to suggest buying when the price is significantly below the 
mean and selling when it is above, aligning with a mean reversion strategy.

# Code
```fex
-1 * zscore(close - ts_mean(close, 20))
```
