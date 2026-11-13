# 6. Equities and Derivatives

[Back to contents](../README.md)

## Summary

A **forward contract** is an OTC transaction between 2 parties whereby the seller promises to sell a specified amount, N, of an
underlying asset at a pre-determined price, K, at a pre-determined specified date, T, and in return the buyer must buy the asset.

This is different to an **option contract** which gives the buyer the right but not the obligation to buy a specified amount of an
underlying asset at a pre-determined price and a pre-determined specified date from the seller. 

Let $S_t$ represent the price at time t of an asset. The **forward payoff function** satisfies f(x) = S - K     
The **forward price**, F, at t=T satisfies F = $\frac{S_0}{D(T)}$ where D(T) is the discount factor to time t. 


## My example

On November 12 2026, Rolls Royce's stock closed at about £13.70. Suppose an investor decides to adopt a bull call spread whereby they buy 1 call
option with a strike price of £14.50 paying a premium of £1 and sells 1 call option with a strike price of £17 receiving a premium of £0.60.
Assume Rolls Royce pays no dividends and the 2 call options have the same expiry date. Calculate the total profit at expiry based on when the share
price is between £12 and £19 for every £1 increment in this range.

**Answer**

The net premium the investor pays to from this strategy is £1 - £0.60 = £0.40. The payoff from the long call is max($s_T$ - 14.50, 0) while the payoff
from the short call is -max($s_T$ - 17, 0). Hence, total payoff = max($s_T$ - 14.50, 0) - max($s_T$ - 17, 0). Thus, total profit = total payoff -0.40 = 
max($s_T$ - 14.50, 0) - max($s_T$ - 17, 0) - 0.40. So, substituting the values for $s_T$ we get 

| Share price at expiry (£) | Total payoff (£) | Total profit (£) |
| ---: | ---: | ---: |
| 12 | 0 | -0.40 |
| 13 | 0 | -0.40 |
| 14 | 0 | -0.40 |
| 15 | 0.50 | 0.10 |
| 16 | 1.50 | 1.10 |
| 17 | 2.50 | 2.10 |
| 18 | 2.50 | 2.10 |
| 19 | 2.50 | 2.10 |

## Solved exercises

### Exercise 6. (from Exercise Sheet 6)



**Answer**

### Exercise 6. (from Exercise Sheet 6)



**Answer**



## Spreadsheet

[06-Equities&Derivatives.xlsx](../spreadsheets/06-Equities&Derivatives.xlsx): what it
does, which cells to change and what to look at.
