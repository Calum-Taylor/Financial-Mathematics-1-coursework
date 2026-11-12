# 5. Stochastic Interest Rates

[Back to contents](../README.md)

## Summary

Interest rates in the future are inherently uncertain, so stochastic interest rates allow us to model this uncertainty
using random variables. Let $R_i$ be the interest rate valid from t = i-1 to t = i. So, at time n$\Delta$t a deposit with principal
P would have grown to

$$
P(1 + R_1 \Delta t)(1 + R_2 \Delta t)...(1 + R_n \Delta t)                             
$$

We often model 1 + $R_i$ ~ lognormal($\mu$, $\sigma^2$) where $R_i$ $\in$ (-1, $\infty$) so 1 + $R_i$ $\in$ (0, $\infty$) and a lognormal distribution doesn’t
take negative values. This is useful when modelling many financial instruments, e.g. a bond price, as these don’t take a negative value either.
Suppose X ~ lognormal($\mu$, $\sigma^2$) then

$$
E(X)= e^{\mu + \frac{\sigma^2}{2}}      
$$

We also assume $R_i$ are **iid (independent, identically distributed)** as this helps to make the maths much easier.
Hence, if $X_i$ ~ lognormal($\mu_i$, $\sigma_i^2$) then $X_1$ + … + $X_n$ ~ lognormal($\mu_1$ + … + $\mu_n$, $\sigma_1^2$ + … + $\sigma_n^2$)


## My example

Suppose we deposit £500 into an investment for 4 years where $R_i$ is the annually compounded rate and $R_i$ are iid with 1 + $R_i$ ~ lognormal(0.09, 0.05).
Find the mean accumulated value after 4 years. 

**Answer:** 

$$
500*e^{4(0.09 + \frac{0.05}{2})} \approx £792.04
$$


## Solved exercises

### Exercise 1.2 (from Exercise Sheet 5)

The interest rate applicable in one year's time for a one year deposit is modelled by the random variable 
and treat is as a continuously compounded annual rate, so that over one year a deposit grows by the factor $e^{R}$.

(a) Find the expected rate E(R)

(b) Find $e^{E(R)}$, the growth factor of your deposit using the expected rate.

(c) Find $E(e^{R})$, the expected growth factor.

(d) Should $E(e^{R})$ not be the same as $e^{E(R)}$?

**Answers**

(a)

$$
E(R) = 0.3(0.003) + 0.7(0.0035) = 0.0335 = 3.35%
$$

(b) 

$$
e^{E(R)} = e^{0.0335} = 1.034067
$$

(c) 

$$
E(e^{R}) = 0.3e^{0.03} + 0.7e^{0.035} = 1.034070
$$

(d) No because e is not a linear function. For an arbitrary linear function g(X), it is true that E(g(X)) = g(E(X))


### Exercise 1.4 (from Exercise Sheet 5)

The interest rate applicable in one year's time for a one year deposit is modelled by the random variable R. You invest P = £1000

(a) Suppose R is the effective rate, so that the deposit grows to (1 + R)P after one year, and take 1 + R to be log-normal, 1 + R ~ log-normal(0.03, 0.01^2)

- (i) What is the amount of cash your deposit will contain at the end of its term?

- (ii) What is the expected amount of cash you will have at the end of the deposit term?

(b) Suppose instead R is the continuously compounded rate, so that the deposit grows to $Pe^{R}$ after one year, and take R to be normal, R ~ N(0.03, $0.01^2$)

- (i) What is the amount of cash your deposit will contain at the end of its term?

- (ii) What is the expected amount of cash you will have at the end of the deposit term?

**Answers**

(ai) A = 1000(1 + R) where 1 + R ~ log-normal(0.03, 0.01^2). So, $A = 1000e^{Y}$ where Y ~ N(0.03, 0.01^2). Since R is a random variable, the terminal amount is also a random variable and so cannot be reduced to a single value.

(aii) Using the definition of the expectation of a log-normal random variable

$$
E(A) = E(1000(1 + R)) = 1000E(1 + R) = 1000e^{0.03 + \frac{0.01^2}{2}} \approx £1030.51
$$

(bi) A = 1000e^{R} where R ~ N(0.03, 0.01^2). By the definition of a log-normal random distribution, $e^{R} ~ log-normal(0.03, 0.01^2)$, meaning $A = 1000e^{R}$ which is exactly the same distribution as the amount in part (a).

(bii) It will also be the same as in part (a) 

$$
E(A) = 1000e^{0.03 + \frac{0.01^2}{2}} \approx £1030.51
$$


## Spreadsheet

[05-StochasticInterestRates.xlsx](../spreadsheets/05-StochasticInterestRates.xlsx): this is the Excel version of the answer to my example. Change any of the inputs in cells C6, C7, C8, C9 of initial investment, number of years, lognormal parameter $\mu$ and lognormal parameter $\sigma^2$ to see how this changes the
theoretical mean accumulated value of the investment. You will find a simulation of 100 different observations as well as the summary statistics of these
observations and a manual check for some statistics. This is because stochastic interest rates are by definition random so we can model different
observations and paths that the final value of the investment took under a lognormal distribution with the specified parameters of $\mu$ and $\sigma^2$.
