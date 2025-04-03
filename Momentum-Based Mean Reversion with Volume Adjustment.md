# Momentum-Based Mean Reversion with Volume Adjustment

# Category:
Price Reversion

# Color:
Violet

# Tags:
momentum, mean reversion, volume adjustment, 5-day delta, 20-day rank

# Description:
This alpha identifies potential mean reversion opportunities by analyzing the momentum of a 
stock's closing price over a 5-day period and adjusting the signal based on the stock's trading volume. 
The approach involves calculating the 5-day difference in closing prices to assess momentum, ranking this
momentum over a 20-day window to identify mean reversion candidates, and then adjusting the signal by the 
rank of the current volume to emphasize trades with significant volume. The final alpha signal is derived by
multiplying the mean reversion signal by the volume adjustment factor.

# Code
```fastexpression
momentum = ts_delta(close, 5);
mean_reversion_signal = -1 * ts_rank(momentum, 20);
volume_adjustment = rank(volume);
alpha_signal = mean_reversion_signal * volume_adjustment;
```
