# 1. Stochastic Interest Rates

[Back to contents](../README.md)

## Summary

Interest rates in the future are inherently uncertain, so stochastic interest rates allow us to model this uncertainty
using random variables. Let R_i be the interest rate valid from t=i-1 to t=i. So, at time $n* $\delta$ t$ a deposit with principal
P would have grown to $P(1 + R_1 * $\delta$ t)(1 + R_2 * $\delta$ t)...(1 + R_n * $\delta$ t)                             
We often model 1+R_i~lognormal($\mu$, (\sigma)^2) where R_i \in (-1, $\infty$) so 1 + Ri \in (0, $\infty$) and a lognormal distribution doesn’t
take negative values. This is useful when modelling many financial instruments, e.g. a bond price, as these don’t take a negative value either.
Suppose X ~ lognormal($\mu$, $\sigma^2$) then E(X)= $e^($\mu$ + \frac{$\sigma^2$}{2}$      
We also assume R_i are iid (independent, identically distributed) as this helps to make the maths much easier.
Hence, if X_i~lognormal($\mu_i$, $\sigma_i^2$) then X_1 + … + X_n~lognormal($\mu_1$ + … + $\mu_n$, $\sigma_1^2$ + … + $\sigma_n^2)


## My example

Suppose we deposit £500 into an investment for 4 years where R_i is the annually compounded rate and R_i are iid with 1 + R_i ~ lognormal(0.09, 0.05).
Find the mean accumulated value after 4 years. 

Answer: 

$$
500*(e^4*(0.09 + \frac{0.05}{2})) = £792.04
$$


## Solved exercises

### Exercise 1.x (from Exercise Sheet 1)

Question, then your solution.

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to look at.
