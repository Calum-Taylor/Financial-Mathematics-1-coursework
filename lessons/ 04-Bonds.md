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
Assume, $s_1$ = the 1-year Gilt rate plus 1% to reflect the additional credit risk of the company defaulting compared to the 
government and $s_3$ = 8%. Find the fair forward rate $f_{1, 3}$ for each of the cases when the 1 year Gilt rate is 3%, 4% and 5% 
and the credit premium is 0.5%, 1% and 1.5%.

**Answers:**
Using the formula above: 
- When $s_1$ = 3% + 0.5% = 3.5%, $f_{n_1, n_2}$ $\approx$ 8.79%
- When $s_1$ = 3% + 1% = 4%, $f_{n_1, n_2}$ $\approx$ 8.53%
- When $s_1$ = 3% + 1.5% = 4% + 0.5% = 4.5%, $f_{n_1, n_2}$ $\approx$ 8.27%
- When $s_1$ = 4% + 1% = 5%, $f_{n_1, n_2}$ $\approx$ 8.01%
- When $s_1$ = 4% + 1.5% = 5% + 0.5% = 5.5%, $f_{n_1, n_2}$ $\approx$ 7.76%
- When $s_1$ = 5% + 1% = 6%, $f_{n_1, n_2}$ $\approx$ 7.50%
- When $s_1$ = 5% + 1.5% = 6.5%, $f_{n_1, n_2}$ $\approx$ 7.25%

As the 1 year Gilt rate increases, the fair forward rate decreases; similarly, as the companies credit premium rises so too does the 
fair forward rate. This is because an increase in  either raise the $s_1$ which raises the denominator  of the fair forward rate formula.
With $s_3$ fixed, the numerator remains unchanged so the fraction becomes smaller, causing a lower value after taking the square root and 
subtracting 1. Hence, there is an inverse relationship between $s_1$ and $f_{1, 3}$ holding $s_3$ constant. More generally, there is an inverse
relationship between $s_{n_1}$ and $f_{n_1, n_2}$ holding $s_{n_2}$ constant. Intuitively, the higher the interest rate in the near future, the
less interest that will have to be paid in the future to achieve	the same overall accumulation of interest the company needs.								



## Solved exercises

### Exercise 1.7 (from Exercise Sheet 4)

Suppose that a broker quotes the price of unit zero-coupon bonds, with maturity times of (0.5, 1, 1.5, 2) years, to be respectively (0.95, 0.92, 0.86, 0.84). What are these numbers also called? Calculate the no-arbitrage price of a 2-year bond with face-value £500000, semi-annual coupons at rate 4% per annum, and no redemption payment.

**Answer**

These numbers are also called the discount factors or zero coupon bond prices; we see that as the maturity time increases, so too does the discount factor. 

Over the course of the 2 years, we will receive 4 semi-annual coupon payments worth £500000($\frac{4%}{2}$) = £10000 at times t = 0.5, 1, 1.5, 2 years. Hence, no arbitrage price, P, = £10000(0.95 + 0.92 + 0.86 + 0.84) = £35700

### Exercise 1.11 (from Exercise Sheet 4)

Show that is a bank offers a FRA (for both loans and deposits) between times $n_1$ and $n_2$ at a forward rate f satisfying

$$
(1 + f)^{n_2 - n_1} < \frac{(1+s_{n_2})^{n_2}}{(1+s_{n_1})^{n_1}}
$$

then there is an arbitrage opportunity.

**Answer**

At time t = 0, the company signs a FRA with the bank to borrow an amount, say £P, between $n_1$ and $n_2$ at the forward rate f. So, they will borrow 

$$
\frac{£P}{(1+s_{n_1})^{n_1}}
$$

for term $n_1$ and deposit 

$$
\frac{£P}{(1+s_{n_1})^{n_1}}
$$

for term $n_2$.

At time t = $n_1$, the loan repayment is 

$$
\frac{£P}{(1+s_{n_1})^{n_1}} \times (1+s_{n_1})^{n_1} = £P
$$

So, to pay this off they will draw down the FRA loan of £1000. Therefore, the net cash flow = 0.

At time t = $n_2$, the deposit will have grown to 

$$
\frac{£P}{(1+s_{n_1})^{n_1}} \times (1+s_{n_2})^{n_2}
$$

The FRA loan repayment is 

$$
£P(1 + f)^{n_2 - n_1}
$$

Consequently, the total net profit is 

$$
P(\frac{(1+s_{n_2})^{n_2}}{(1+s_{n_1})^{n_1}} - (1 + f)^{n_2 - n_1}) > 0
$$

which is strictly positive by our assumption, thus creating an arbitrage opportunity.

## Spreadsheet

[04-Bonds.xlsx](../spreadsheets/04-Bonds.xlsx): this is the Excel version of the answer to my example. In the sensitivity analysis table you can 
change any of the 1 year Gilt rates, the credit premiums and $s_3$ to see how this influences $f_{1, 3}$.
