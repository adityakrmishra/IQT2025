Name: Custom Alpha - Low Price Reversion​

Category: Price Reversion​


# Color: 
Sky Blue​

# Tags: 
low price, time-series rank, price reversion, 9-day window​

# Description: 
This alpha identifies stocks whose 'low' prices have been relatively high over
the past 9 days but are currently lower, suggesting a potential price reversion. It is constructed by 
computing the cross-sectional rank of the 'low' prices, followed by the time-series rank over a 9-day 
window, and inverting the result to highlight potential buy opportunities.

# code
```fastexpression
(-1 * Ts_Rank(rank(low), 9))
```
