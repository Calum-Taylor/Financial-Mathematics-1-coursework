# 4. Bonds

[Back to contents](../README.md)

## Summary

These are a contract issued by company and governments, for example, designed to raise capital. In exchange for the
investor(s) lending money to the issuer they receive regular coupon payments, though not in the case of 
zero-coupon bonds and the repayment of the principal they lent out at a set maturity date. 

The **bond yield** is the **IRR** of the investment in a bond. 

In practice, interest rates vary depending on the duration of a deposit or loan which is why we use **spot rates** to allow
us to compare the impact of interest rates for different maturities. The spot rate is the effective annual rate for a
deposit held to a maturity date T defined as $s_T$ = $(1 + r_T * T)^\frac{1}{T}$

Also, spot rates are connected to discount rates through the equation  D(T) = $\frac{1}{(1 + s_T)^T}$
The function $s_T$ is the spot rate curve. 

To remove uncertainty as to what the interest rate in the future will be for a specified maturity, 2 parties can enter
into an **over the counter (OTC) forward rate agreement (FRA)** to specify this interest rate. The forward rate $f_{n_1, n_2}$ from
times $n_1$ and $n_2$ satisfies 

$$
(1 + f_{n_1, n_2})^{n_2 - n_1} = \frac{(1 + s_{n_2})^{n_2}}{(1 + s_{n_1})^{n_1}}
$$


## My example

A rare earth mine will bring in £1mn at the end of the 1st year so the company wishes to place this into a deposit for 2 years.
Assume, $s_1$ = the 1-year treasury rate plus 1% to reflect the additional credit risk of the company defaulting compared to the 
government and $s_3$ = 8%. Find the fair forward rate $f_{1, 3}$. 

## Solved exercises

### Exercise 1.x (from Exercise Sheet 1)

Question, then your solution.

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to look at
