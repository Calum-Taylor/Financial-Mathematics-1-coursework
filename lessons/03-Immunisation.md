# 3. Immunisation of assets and liabilities

[Back to contents](../README.md)

## Summary

**Assets** refer to positive future cash flows while **liabilities** refer to negative future cash flows, i.e. outgoing payments.

So, the **NPV** is the sum of assets and liabilities. 

The **effective duration** of a cash flow stream is 

$$
\nu = - \frac{NPV'(r)}{NPV(r)}
$$

which identifies how sensitive the NPV is to r. 

The **duration** of a cash flow stream is $\tau = \frac{\sum_{i=1}^n t_i\ C_i D(t_i)}{NPV(r)}$ where $C_i$ and D($t_i$) represent cash flows
and discount factors at time i where i = 1, 2, ..., n. Thus, duration is a weighted average of the times we receive a cash flow,
weighted by the NPV of the cash flow and is measured in years.

It is said that a sequence of cash flows **immunised to order 0** if NPV(r) = 0, in other words assets and liabilities are matched.

A sequence of cash flows is **immunised to order 1** if NPV(r) = 0 and NPV’(r) = 0; this implies that cash flows must be immunised
to order 0, we are delta neutral and the duration of assets and liabilities is matched.  

A sequence of cash flows is **Reddington immune** if NPV(r) = 0, NPV’(r) = 0 and NPV’’(r) \geq 0; this implies that cash flows must be
immunised to order 1, we are long gamma and the convexity of assets is greater than the convexity of liabilities. 
Hence, Reddington immunisation means that if interest rates move up or down a bit, NPV(r) increases which helps to reduce market risk. 


## My example

Suppose a company invests £5mn in a rare earth mine which will generate £1mn, £2mn, £3mn and £4mn at the ends of the 1st, 2nd, 3rd and
4th years, respectively. Also, there are additional liabilities of £3mn and £0.5mn at the ends of the 2nd and 4th years, respectively.
Determine whether Reddington immunisation can be achieved.

Answer: 

$$
NPV(r) = - \frac{5}{(1 + r)^0} + \frac{1}{(1 + r)^1} + \frac{2}{(1 + r)^2} - \frac{3}{(1 + r)^2} + \frac{3}{(1 + r)^3} + \frac{4}{(1 + r)^4} - \frac{0.5}{(1 + r)^4} = - \frac{5}{(1 + r)^0} + \frac{1}{(1 + r)^1} - \frac{1}{(1 + r)^2} + \frac{3}{(1 + r)^3} + \frac{3.5}{(1 + r)^4}
$$


$$
NPV'(r) = - \frac{1}{(1 + r)^2} + \frac{2}{(1 + r)^3} - \frac{9}{(1 + r)^4} - \frac{14}{(1 + r)^4}
$$

Using software, such as Excel (see my Excel document attached), you will see that There is no interest rate, r, such that both NPV(r) = 0 and
NPV'(r) = 0 meaning 1st order immunisation can't be achieved. This implies that Reddington immunisation can't be achieved either because 1st
order immunisation is a necessary condition for Reddington immunisation.


## Solved exercises

### Exercise 3.2 (from Exercise Sheet 3)
Suppose the nominal interest rate is 4% and is continuously compounded. Compute the:
- present value,
- duration,
- effective duration, and
- convexity

of the following cash-flow streams:
- (a) An investment that pays you £1000 at the end of year 2 and £500 at the end of year 3.
- (b) A liability that requires you to pay £1500 at the end of years 3 and 4.

Answers:

(a) 

$$ 
PV = 1{,}000*e^{-0.04(2)} + 500*e^{-0.04(3)} \approx £1{,}370
$$

It can be shown that the duration and effective duration of interest continuously compounded are equal to 
each other, though we will not prove this here. Hence,

$$
\tau = \nu = \frac{2 * 1{,}000 * e^{0.04(2)} + 3 * 500 * e^{-0.04(3)}}{PV} \approx 2.32 years
$$

The convexity is:

$$
c = \frac{(2^2) * 1{,}000 * e^{-0.04(2)} + (3^2) * 500 * e^{-0.04(3)}}{PV} \approx 5.62
$$


(b) 

$$
PV = 1{,}500e^{-0.04(3)} + 1{,}500e^{-0.04(4)} \approx £2{,}610
$$

The duration and convexity are both equal to:

$$
\tau = \nu = \frac{3 * 1{,}500 * e^{-0.04(3)} + 4 * 1{,}500 * e^{-0.04(4)}}{PV} \approx 3.49 years
$$

The convexity is:

$$
c = \frac{(3^2) * 1{,}500 * e^{-0.04(3)} + (4^2) * 1{,}500 * e^{-0.04(4)}}{PV} \approx 5.62
$$


### Exercise 3.6 (from Exercise Sheet 3)
An investor has one liability of £20,000 to be paid in 3.5 years and another of £18,000
to be paid in 6 years. The interest rate is 10% compounded annually. Show that we cannot achieve Redington
immunisation of these liabilities with 4 year and 7 year zero coupon bonds by trying to construct a portfolio
of these bonds that does Redington immunise them.

**Answer:** 

$$
NPV(r) = - \frac{20{,}000}{(1.1)^3.5} + \frac{P}{(1.1)^4} - \frac{18{,}000}{(1.1)^6} + \frac{Q}{(1.1)^7}
$$


$$
NPV'(r) = \frac{70{,}000}{(1.1)^4.5} - \frac{4P}{(1.1)^5} + \frac{6*18{,}000}{(1.1)^7} - \frac{7Q}{(1.1)^8}
$$

Setting NPV(10%) = 0 and NPV'(10%) = 0 we get a pair of simultaneous equations which we can solve to get
P $\approx$ 29, 400 and Q $\approx$ 8, 550

$$
NPV''(r) = - \frac{4.5 * 70{,}000}{(1.1)^5.5} + \frac{20P}{(1.1)^6} - \frac{42 * 18{,}000}{(1.1)^8} + \frac{56Q}{(1.1)^9}
$$

Substitutitng the values for P and Q we get NPV''(10%) $\approx$ -4198.923397 < 0 
Hence, Reddington immunisation cannot be achieved using a compbination of 4 year and 7 year zero coupon bonds.



## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to
