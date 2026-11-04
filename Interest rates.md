# 1. Interest rates

[Back to contents](../README.md)

## Summary

Interest rates help to explain how a principal amount £P, also referred to the amount we borrow, grows over time under a nominal
interest rate r. However, interest rates can be quoted in a variety of different ways. 
- For example, if interest was **compounded n times a year**, then in t years the principal would have grown to $P(1 + \frac{r}{n})^{nt}$ 
- Also, interest can be **continuously compounded** where interest is being added and reinvested at every moment in time leading to exponential
growth in the principal amount. In this case, after t years the principal would have grown to $P(e^{rt})$

Hence, to compare the effect of different compounding frequencies we need to use **effective annual interest rates**. 
- When interest is compounded n times a year then reff = $(1 + \frac{r}{n})^n -1 $
- When interest is continuously compounded, reff = $e^r -1 $

## My example

Suppose I take out a £30,000 loan at the 10-year gilt yield of 5.30%, as of 30 Octoer 2026, to cover tuition fees for the duration of my BSc where
each year study costs £10,000 and I am required to pay fees for every year upfront at the start of the 1st year.  How much will the loan be worth
in 10 years if interest is: 
- (a) Compounded annually     
- (b) Compounded quarterly
- (c) Compounded continuously
Calculate the effective rates in each of the scenarios to confirm which gives the lowest effective rate.

**Answers:**
(a) 

$$
30000*((1 + 0.053)^{10}) = £50281.12
$$

(b) 

$$
30000*((1 + \frac{0.053}{4}))^{4*10} = £50790.88
$$

(c) 

$$
30000*(e^{0.053(10)}) = £50967.97
$$

Interest continuously compounded yields the highest accumulated balance and effective annual rate because interest is being applied at every single
moment in time. This is in contrast to interest being applied annually at the end of every year.


## Solved exercises

### Exercise 1.5 (from Exercise Sheet 1)

Consider an asset that, for an initial investment of £1,000, gives you a payment of £1,200 in two years’ time (the initial investment £1,000
is not returned to you). 
(a) In relation to this investment:
- (i) What is the return?
- (ii) What is the profit?
- (iii) What is the rate of return over the 2 years?
- (iv) What is the annualised rate of return?
- (v) What is the IRR?

(b) Suppose the prevailing interest rate was 7%. Would you consider this a good investment:
- (i) If there is no tax?
- (ii) If the payment is taxed at 5%?

**Answers:**

(ai) Return = P_final = £1200

(aii) Profit = P_final - P = £1200 - £1000 = £200

(aiii) Rate of return, $R = \frac{1{,}200 - 1{,}000}{1{,}000} = 20\%$

(aiv) The annualised rate of return is:

$$
r = \frac{R}{T} = \frac{0.2}{2} = 10\%
$$

(v)Since there is only one payment, the IRR is the same as the equivalent effective interest rate. To check this via the definition, the IRR is the solution of:

$$
1{,}000 = \frac{1{,}200}{(1+r)^2} \implies r = \sqrt{1.2} - 1 = 0.0954
$$

bi) If there is no tax, IRR = 9.54% > 7% = nominal rate so the investment is good as it exceeds the opportunity
cost of holding cash in the bank and earning interest on the balance.

bii) If the payment is subject to a 5% tax, the IRR is the solution of:

$$
1{,}000 = \frac{1{,}200(0.95)}{(1+r)^2} 
$$ 

This implies

$$
r = \sqrt{1.14} - 1 = 0.0677
$$

IRR = 6.77% < 7% = nominal rate so the investment would not considered to be a good one.


### Excercise 1.8 (from Exercise Sheet 1)
Consider a deposit of £1 that accrues a nominal interest rate of 100% compounded n times a year. Calculate how
much money you will have in the bank in one year as n tends to $\infty$.

**Answer:**

$$
\lim_{n \to \infty}\left(1 + \frac{1}{n}\right)^{n} = e \approx £2.72
$$

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to
