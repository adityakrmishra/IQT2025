# Volume-Adjusted Price Momentum

**Category:**
Price Momentum

**Color:**
Yellow

**Tags:**
price momentum, volume change, rank correlation, 5-day average, 5-day standard deviation

**Description:**
This alpha captures the interaction between price momentum and volume changes to identify potential trading opportunities.
It computes the 1-day price momentum and 1-day volume change, ranks them, and measures their deviations from their 
respective 5-day moving averages. The product of these deviations is averaged over a 5-day window and normalized by the
product of their 5-day standard deviations. The result is then ranked over the past 5 days and inverted to generate the final
alpha signal. A higher alpha value suggests a stronger potential for price movement influenced by recent volume changes.

**Code:**
```fastexpression
ts_rank(
    ts_mean(
        (rank(ts_delta(close, 1)) - ts_mean(rank(ts_delta(close, 1)), 5)) *
        (rank(ts_delta(volume, 1)) - ts_mean(rank(ts_delta(volume, 1)), 5)),
        5
    ) /
    (ts_std_dev(rank(ts_delta(close, 1)), 5) * ts_std_dev(rank(ts_delta(volume, 1)), 5)),
    5
) * -1
```
