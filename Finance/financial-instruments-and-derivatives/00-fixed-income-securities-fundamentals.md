# Fixed Income Securities Fundamentals

## Core fixed-income instruments

### Bonds

- Time to maturity: more than 1 year
- Periodic interest payments (coupons)
- Principal repaid at maturity (is the loaned amount)
- Example: Government bond, 5% coupon, 10-year maturity

A bond is a loan that an investor gives to a bond issuer (e.g. a government or a company). The issuer receives the principal today and promises to repay it on the maturity date. In exchange, the issuer pays a fixed interest amount, the coupon, at regular intervals (e.g. every 3 months, 6 months, or 1 year) until maturity. The coupon rate and the maturity date are fixed when the bond is issued. The market price of the bond can change if interest rates or the credit quality of the issuer change. The investor knows the future cash flows in advance, and this is why a bond is a fixed-income security.

Bonds can also be traded publicly. Some of them are very liquid and change hands every day in the open market. The underlying idea is that the investor lends money to the issuer, but does not have to hold the loan until maturity: the investor can sell the bond to another investor, who then receives the remaining coupons and the principal at maturity.

### Notes

Notes are similar to bonds, but their time to maturity is between 1 and 10 years. The term is mostly used for government debt (e.g. US Treasury notes), but the underlying mechanics are the same as for bonds: periodic coupon payments and repayment of the principal at maturity.

### Bills

Bills have a short time to maturity (1 year or less). Because the maturity is so short, periodic coupon payments make little sense, so bills pay no coupons. Instead, the investor buys the bill at a discount to its face value and receives the full face value at maturity. The difference between the two amounts is the interest. For this reason, we can value a bill directly with a discount factor: the price is the face value discounted from the maturity date to today.

Bills with very short maturities (e.g. 1 month or 90 days) are very common.

### CDs (Certificates of Deposit)

Deposits are normally payable on demand: the client can withdraw the money at any time, without notice. Because the money can be withdrawn at any moment, a demand deposit has a very short duration, close to zero, and its value is not sensitive to changes in interest rates.

A certificate of deposit (CD) is different. The client agrees to leave a fixed amount in the bank until a maturity date (e.g. 3 months, 6 months, or 1 year). In exchange, the bank pays a fixed interest rate, usually higher than the rate on a demand deposit. If the client withdraws the money before maturity, the bank applies a penalty. Because the cash flows are fixed in advance, a CD is a fixed-income instrument, like a bond or a bill.

The main problem of a CD is its limited liquidity. Unlike bonds and bills, a CD is a contract between the client and one bank, and there is no market where the client can easily resell this debt to another investor. The only way to recover the money before maturity is to pay the penalty to the bank. Only large CDs issued to institutions (negotiable CDs) can be sold in a secondary market.

## Pricing of a Fixed Income Security

The price of a fixed-income security is the present value of all the cash flows that the security pays in the future. We must discount each cash flow back to today, and the size of the discount depends on two things, the yield and the time at which the cash flow arrives. The price is the sum of all these discounted cash flows:

$$P=\sum_{t=1}^{n} \frac{CF_t}{(1+y)^t}$$

- $P$ is the price of the security today.
- $t$ is the time of each cash flow, in years.
- $n$ is the number of cash flows.
- $CF_t$ is the cash flow paid at time $t$ (a coupon, or the last coupon plus the principal at maturity).
- $y$ is the yield to maturity, that is the discount rate that the market applies to the security.

The term $1/(1+y)^t$ is the discount factor. It converts one unit of money paid at time $t$ into money of today. Two effects control its size:

- The yield. A high yield gives a small discount factor, so the price is low. A low yield gives a large discount factor, so the price is high. This is why the price of a fixed-income security moves in the opposite direction to the yield.
- The time. The exponent $t$ grows with the time to the cash flow, so a distant cash flow receives a stronger discount than a near cash flow of the same size. A cash flow at year 10 contributes much less to the price than the same cash flow at year 1.

The yield $y$ is the single rate that makes the sum of the discounted cash flows equal to the market price. It is therefore the internal rate of return of the security, if the investor buys at the price $P$, holds the security to maturity, and reinvests each coupon at the rate $y$, the investor earns exactly $y$ per year.

### Clean and Dirty Prices

The **dirty price**, or **full price**, is the price $P$ of the fixed-income security defined above. It is the **cash that the buyer pays** on the settlement date. Between two coupon dates the times $t$ are not whole years, e.g. 3 months after the last coupon of an annual bond the cash flows arrive at $t = 0.75, 1.75, \dots$

The **clean price** is the dirty price minus the **accrued interest** ($AI$), the part of the next coupon that the seller earned from the last coupon date to the settlement date. Thus the accrued interest grows with the time. The buyer pays the clean price plus the accrued interest, i.e. the dirty price, because the buyer receives the full next coupon.

$$P_{clean} = P_{dirty} - AI$$

$$AI = \frac{C}{f} \times \frac{\text{time since the last coupon}}{\text{time between two coupons}} = C \times \text{years since the last coupon}$$

$C$ is the annual coupon and $f$ is the frequency of payment (1, 2 or 4 coupons in one year), so $\frac{C}{f}$ is one coupon. In years, the frequency cancels, because one coupon accrues in $\frac{1}{f}$ years. The day-count rule of the security sets how to count the time (see [Interest Rate Curves Fundamentals](01-interest-rates-curves-fundamentals.md)).

In the example above ($C = 5$, $f = 1$), $AI = 5 \times \frac{3}{12} = 1.25$. The other 9 months, until the next coupon, belong to the buyer.

The chart shows a 10-year bond with a 3% coupon paid every six months ($\frac{C}{f} = 1.5$) and a constant yield of 5%.

![Dirty price and clean price of a 10-year bond with a constant yield](Attachments/dirty-vs-clean-price.svg)

- The dirty price draws a **saw-tooth**. It rises with the accrued interest and falls by the coupon on each coupon date. This fall is **not a loss**, because the money moves from the price to the cash of the holder.
- The clean price rises **smoothly** to par. It stays below 100, because the 3% coupon is lower than the 5% yield. Its change is **not the return**, because it does not include the accrued interest.

**Why the market quotes the clean price**

The accrued interest grows linearly and goes back to zero on the coupon date, so it absorbs the jump of the dirty price. The clean price stays continuous, so it lets you compare the prices of different bonds, also when their coupon calendars are different. Screens, trading desks and futures quote the clean price. The settlement and the return always use the dirty price.

## Macaulay Duration

The Macaulay duration is the weighted average time, in years, at which an investor receives the cash flows of a fixed-income security. Each cash flow is weighted by its present value. The intuition is that it is the average time in which you recover the money that you invested. Each time counts in proportion to the money, in value of today, that arrives at that time. For a security with $m$ cash flows per year, the formula is

$$D_{Mac}=\frac{1}{P}\sum_{k=1}^{N} t_k \cdot \frac{CF_{t_k}}{\left(1+\frac{y}{m}\right)^{m t_k}}$$

- $m$ is the compounding frequency, the number of cash flows per year (e.g. $m = 2$ for semiannual coupons).
- $t_k = k/m$ is the time of the $k$-th cash flow, in years.
- $N = m T$ is the number of cash flows, and $T$ is the maturity in years.
- $CF_{t_k}$ is the cash flow paid at time $t_k$ (coupon, or coupon plus principal at maturity).
- $P$ is the price of the security.
- $y$ is the yield to maturity, quoted as a nominal annual rate with $m$ compounding periods per year. It is the discount rate that makes the sum of the discounted cash flows equal to $P$.

In the particular case of one cash flow per year ($m = 1$), the times are whole years ($t_k = k$), and the formula becomes

$$D_{Mac}=\frac{1}{P}\sum_{t=1}^{n} t \cdot \frac{CF_t}{(1+y)^t}$$

The formula sums all the cash flows, each multiplied by the time at which it is paid and discounted at the yield to maturity with compound interest. The sum is then divided by the price of the security. The division by $P$ is what turns the sum into an average. A weighted average of the times $t$ is the sum of each $t$ multiplied by a weight, where all the weights add up to 1. In the formula, the weight of each time $t$ is its discounted cash flow divided by $P$. Because $y$ is the rate that makes the discounted cash flows add up to the price:

$$\sum_{t=1}^{n} \frac{CF_t}{(1+y)^t} = P$$

the weights add up to exactly 1, and $D_{Mac}$ is a true average of the times $t$. Each time $t$ counts in proportion to the share of the price that its cash flow represents. A cash flow that is large or paid soon has a large present value and pulls the average towards its time. A cash flow that is small or paid late has a small present value and pulls the average less.

A zero-coupon bond is the simplest check. It has one cash flow at maturity, so that cash flow is the whole price, its weight is 1, and the Macaulay duration equals the maturity. A coupon bond pays part of the price before maturity, so its Macaulay duration is shorter than the maturity.

The times $t_k$ are always in years, so the Macaulay duration is a time in years for all compounding frequencies. With continuous compounding ($m \to \infty$), the discount factor becomes $e^{-y t_k}$, and the Macaulay duration is

$$D_{Mac}=\frac{1}{P}\sum_{k=1}^{N} t_k \cdot CF_{t_k} e^{-y t_k}$$

**Example**

A bond has a face value of 100 and a maturity of 4 years. It pays an annual coupon of 5%. The yield to maturity (YTM) is 4%.

| Year ($t$) | Cash flow ($CF_t$) | Present value of the cash flow ($PV_t$) | $t \times PV_t$ |
| :--------: | :----------------: | :-------------------------------------: | :--------------: |
|     1      |         5          |                  4.808                  |      4.808       |
|     2      |         5          |                  4.623                  |      9.246       |
|     3      |         5          |                  4.445                  |      13.335      |
|     4      |        105         |                 89.754                  |     359.016      |
| **Total**  |                    |                 103.630                 |     386.405      |

With annual compounding ($m = 1$), the Macaulay duration is

$$D_{Mac}=\frac{1}{103.630}\left[1 \cdot \frac{5}{1.04} + 2 \cdot \frac{5}{1.04^2} + 3 \cdot \frac{5}{1.04^3} + 4 \cdot \frac{105}{1.04^4}\right]=\frac{386.405}{103.630}=3.73$$

If the yield of 4% uses continuous compounding, the price is 103.329, and the Macaulay duration is

$$D_{Mac}=\frac{1}{103.329}\left[1 \cdot 5 e^{-0.04} + 2 \cdot 5 e^{-0.08} + 3 \cdot 5 e^{-0.12} + 4 \cdot 105 e^{-0.16}\right]=\frac{385.239}{103.329}=3.73$$

**Example with semiannual cash flows**

The same bond pays its 5% coupon in two parts of 2.5 every six months ($m = 2$). The yield to maturity is 4% with semiannual compounding, so each period has a rate of 2%.

| Time ($t_k$) | Cash flow ($CF_{t_k}$) | Present value ($PV_{t_k}$) | $t_k \times PV_{t_k}$ |
| :----------: | :--------------------: | :------------------------: | :-------------------: |
|     0.5      |          2.5           |           2.451            |         1.225         |
|     1.0      |          2.5           |           2.403            |         2.403         |
|     1.5      |          2.5           |           2.356            |         3.534         |
|     2.0      |          2.5           |           2.310            |         4.619         |
|     2.5      |          2.5           |           2.264            |         5.661         |
|     3.0      |          2.5           |           2.220            |         6.660         |
|     3.5      |          2.5           |           2.176            |         7.617         |
|     4.0      |         102.5          |           87.483           |        349.931        |
|  **Total**   |                        |          103.663           |        381.650        |

With semiannual compounding ($m = 2$), the Macaulay duration is

$$D_{Mac}=\frac{1}{103.663}\left[\sum_{k=1}^{7} \frac{k}{2} \cdot \frac{2.5}{1.02^{k}} + 4 \cdot \frac{102.5}{1.02^{8}}\right]=\frac{381.650}{103.663}=3.68$$

If the yield of 4% uses continuous compounding, the price is 103.512, and the Macaulay duration is

$$D_{Mac}=\frac{1}{103.512}\left[\sum_{k=1}^{7} \frac{k}{2} \cdot 2.5 e^{-0.04 \cdot \frac{k}{2}} + 4 \cdot 102.5 e^{-0.16}\right]=\frac{381.067}{103.512}=3.68$$

The Macaulay duration is shorter than the 3.73 years of the annual bond, because half of each coupon arrives six months earlier.

## Modified Duration

The Modified Duration measures the sensitivity of the price of the security when there are changes in the interest rates. When the yield rises, the price of a fixed-income security falls. The modified duration measures how much: a modified duration of 3.59 means that the price falls by approximately 3.59% when the yield rises by 1 percentage point (e.g. from 4% to 5%). For a security with $m$ cash flows per year, it is the Macaulay duration divided by $\left(1 + \frac{y}{m}\right)$

$$D_{Mod}=\frac{D_{Mac}}{1+\frac{y}{m}}$$

- $D_{Mac}$ is the Macaulay duration, in years.
- $m$ is the compounding frequency, the number of cash flows per year.
- $y$ is the yield to maturity, quoted as a nominal annual rate with $m$ compounding periods per year.

In the particular case of one cash flow per year ($m = 1$), the formula becomes

$$D_{Mod}=\frac{D_{Mac}}{1+y}$$

With continuous compounding ($m \to \infty$), the term $\frac{y}{m}$ goes to zero, and the modified duration is equal to the Macaulay duration

$$D_{Mod}=D_{Mac}$$

With the modified duration, the percentage change in price for a small change in yield is:

$$\frac{\Delta P}{P}\approx -D_{Mod}\times\Delta y$$

- $\Delta y$ is the change in the yield (e.g. $0.01$ for a rise from 4% to 5%).
- $\Delta P / P$ is the percentage change in the price.
- The minus sign shows that the price moves in the opposite direction to the yield.

The two durations measure different things. The Macaulay duration is a time, in years. The modified duration is a sensitivity of the price to the yield. The division by $\left(1 + \frac{y}{m}\right)$ converts the time into the sensitivity. With continuous compounding, the time and the sensitivity have the same value.

> [!NOTE]
> **Why is this an approximation?**
>
> The derivation below gives an exact result, but only for an infinitely small change in yield: $\frac{1}{P}\frac{\mathrm{d}P}{\mathrm{d}y} = -D_{Mod}$. This is the slope of the price curve at the current yield. The formula above replaces the infinitely small change $\mathrm{d}y$ with a finite change $\Delta y$, so it follows the straight line with that slope instead of the curve. The price curve is convex (it bends upwards), and the line is below the curve everywhere except at the current yield. For a small $\Delta y$ the gap is negligible. For a large $\Delta y$ the gap grows, and the true fall in price is smaller than the formula predicts. In Taylor expansion terms, the formula keeps only the first-order term and drops the convexity term. See [Appendix 1](#appendix-1-taylor-polynomial-and-the-relative-price-change) for how the Taylor polynomial gives this approximation and its error.


**Example**

The bond above has $D_{Mac}=3.73$ and $y=4$%, so $D_{Mod}=3.73/1.04=3.59$. If the yield rises by 1% (from 4% to 5%), the price falls by approximately $\Delta P/P \approx -D_{Mod} \times \Delta y = -3.59 \times 0.01 = -3.59$%. The approximation is a first-order one. For large changes in yield, the convexity of the price curve makes the true fall smaller and the true rise larger.

With semiannual cash flows ($m = 2$), the same bond has $D_{Mac}=3.68$, so $D_{Mod}=3.68/1.02=3.61$. If the yield of 4% uses continuous compounding, $D_{Mod}=D_{Mac}=3.73$ for the annual bond and $D_{Mod}=D_{Mac}=3.68$ for the semiannual bond.

**Derivation**

To derive the modified duration, we start from the price of the security discounted with compound interest:

$$P = \sum_{t=1}^{n} \frac{CF_t}{(1+y)^t}$$

We then differentiate with respect to the yield to maturity $y$:


$$\frac{\mathrm{d} P }{\mathrm{d} y} = \frac{\mathrm{d}}{\mathrm{d} y} \sum_{t=1}^{n} \frac{CF_t}{(1+y)^t} = \frac{\mathrm{d}}{\mathrm{d} y} \sum_{t=1}^{n} CF_t (1+y)^{-t} $$

Applying the chain rule:

$$\frac{\mathrm{d} f(g(x))}{\mathrm{d} x} = \frac{\mathrm{d} f(g(x))}{\mathrm{d} g(x)} \frac{\mathrm{d} g(x)}{\mathrm{d} x} $$

With $u = 1 + y$:

$$\frac{\mathrm{d}}{\mathrm{d} y} \sum_{t=1}^{n} CF_t (1+y)^{-t} = \left[\frac{\mathrm{d}}{\mathrm{d} u} \sum_{t=1}^{n} CF_t u^{-t}\right] \frac{\mathrm{d} u}{\mathrm{d} y}$$

We use the derivative of a sum rule, the constant multiple rule, the derivative of a constant rule, and the derivative of the variable rule:

$$\frac{\mathrm{d} (f(x) + g(x))}{\mathrm{d} x} = \frac{\mathrm{d} f(x)}{\mathrm{d} x} + \frac{\mathrm{d} g(x)}{\mathrm{d} x}$$

$$\frac{\mathrm{d}C}{\mathrm{d} x} = 0$$

$$\frac{\mathrm{d}x}{\mathrm{d} x} = 1$$

With these rules, the derivative of $u$ with respect to $y$ is 1, so the chain rule factor disappears:

$$\frac{\mathrm{d} u}{\mathrm{d} y} = \frac{\mathrm{d} 1}{\mathrm{d} y} + \frac{\mathrm{d} y}{\mathrm{d} y} = 1$$

$$\left[\frac{\mathrm{d}}{\mathrm{d} u} \sum_{t=1}^{n} CF_t u^{-t}\right] \frac{\mathrm{d} u}{\mathrm{d} y} = \frac{\mathrm{d}}{\mathrm{d} u} \sum_{t=1}^{n} CF_t u^{-t}$$

Applying the power rule:

$$\frac{\mathrm{d} x^n}{\mathrm{d} x} = n x ^{n-1}$$

$$\frac{\mathrm{d}}{\mathrm{d} u} \sum_{t=1}^{n} CF_t u^{-t} = \sum_{t=1}^{n} - t CF_t u^{-t - 1} = \sum_{t=1}^{n} -t \frac{CF_t}{u^{t + 1}} =  \sum_{t=1}^{n} -t \frac{CF_t}{(1+y)^{t + 1}} = - \frac{1}{1 + y} \sum_{t=1}^{n} t \cdot \frac{CF_t}{(1+y)^t}$$

Therefore:

$$\frac{1}{P} \frac{\mathrm{d} P }{\mathrm{d} y} = - \frac{1}{1 + y} \frac{1}{P} \sum_{t=1}^{n} t \cdot \frac{CF_t}{(1+y)^t} = - \frac{D_{Mac}}{1+y} = -D_{Mod}$$

With $m$ cash flows per year, the same steps with $u = 1 + \frac{y}{m}$ give $\frac{\mathrm{d} u}{\mathrm{d} y} = \frac{1}{m}$. This factor cancels the $m$ of the exponent $-m t_k$.

$$\frac{1}{P} \frac{\mathrm{d} P }{\mathrm{d} y} = \frac{1}{P} \sum_{k=1}^{N} CF_{t_k} \left(-m t_k\right) \left(1+\frac{y}{m}\right)^{-m t_k - 1} \frac{1}{m} = - \frac{1}{1 + \frac{y}{m}} \frac{1}{P} \sum_{k=1}^{N} t_k \cdot \frac{CF_{t_k}}{\left(1+\frac{y}{m}\right)^{m t_k}} = - \frac{D_{Mac}}{1+\frac{y}{m}} = -D_{Mod}$$

With continuous compounding, the derivative of $e^{-y t_k}$ is $-t_k e^{-y t_k}$, so no factor remains.

$$\frac{1}{P} \frac{\mathrm{d} P }{\mathrm{d} y} = \frac{1}{P} \sum_{k=1}^{N} -t_k \cdot CF_{t_k} e^{-y t_k} = -D_{Mac} = -D_{Mod}$$

## Money Duration or Dollar Duration

The money duration, or dollar duration, is the modified duration multiplied by the price of the security. The modified duration gives the sensitivity as a percentage of the price. The money duration gives the same sensitivity as an amount of currency.

$$D_{Money} = D_{Mod} \times P$$

The change in price for a change in yield is then:

$$\Delta P \approx -D_{Money} \times \Delta y$$

## Convexity

As we saw, the modified duration is a linear approximation. If the change in the yield is large, this approximation becomes unreliable, because the price curve is convex, not a straight line. Convexity is the second-order term that corrects this error.

The convexity measures the curvature of the price-yield curve. It improves the approximation by adding a second-order term to the formula. The convexity is the second derivative of the price with respect to the yield, divided by the price:

$$C=\frac{1}{P}\frac{d^2P}{dy^2}=\frac{1}{P}\sum_{t=1}^{n} \frac{t(t+1) \cdot CF_t}{(1+y)^{t+2}}$$

With this term, the second-order approximation of the price change is:

$$\frac{\Delta P}{P} \approx -D_{Mod} \cdot \Delta y + \frac{1}{2} C \cdot (\Delta y)^2$$

> [!NOTE]
> This formula is a second-order Taylor polynomial of the price around the current yield. The first-order term is the duration. The second-order term is the convexity. The formula ignores the terms of order three and higher, so it is still an approximation. See [Appendix 1](#appendix-1-taylor-polynomial-and-the-relative-price-change) for the rationale of the Taylor polynomial and how each term maps to duration and convexity.

For a bond with fixed cash flows, the convexity is always positive. Negative convexity can appear only when the cash flows depend on the yield, for example in callable bonds or mortgage-backed securities. The formula above does not apply to those securities, because it treats the $CF_t$ as constants. A positive convexity always gives a better result than the simpler linear approximation, whatever the interest rates do. If the interest rates rise, the convexity term reduces the fall in price that the linear approximation computes. If the interest rates fall, the convexity term increases the rise in price that the linear approximation computes.

The effect of the convexity is small for small changes in the interest rates. It becomes important for large changes, for example when a long period of time has passed and the interest rates have moved far from their initial level.

**Example**

We continue with the bond above: $D_{Mod}=3.59$ and $y=4$%. We take a convexity of $C=70$ to make the effect visible.

For a small change, $\Delta y=0.002$:

- **Linear:** $-D_{Mod}\cdot\Delta y = -3.59\times0.002 = -0.718$%
- **Convexity term:** $\tfrac{1}{2}C\cdot(\Delta y)^2 = \tfrac{1}{2}\times70\times0.002^2 = +0.014$%
- **Second order:** $-0.718 + 0.014 = -0.704$%

For a large change, $\Delta y=0.02$:

- **Linear:** $-D_{Mod}\cdot\Delta y = -3.59\times0.02 = -7.18$%
- **Convexity term:** $\tfrac{1}{2}C\cdot(\Delta y)^2 = \tfrac{1}{2}\times70\times0.02^2 = +1.40$%
- **Second order:** $-7.18 + 1.40 = -5.78$%

| Change in yield | Linear approximation | Convexity term | Second-order approximation |
| :-------------: | :------------------: | :------------: | :------------------------: |
|     +0.2%       |       -0.718%        |    +0.014%     |          -0.704%           |
|     +2%         |       -7.18%         |    +1.40%      |          -5.78%            |

The linear term grows in proportion to $\Delta y$. The convexity term grows in proportion to $(\Delta y)^2$. The change in yield is 10 times larger, so the linear term is 10 times larger, but the convexity term is 100 times larger. For the small change, the correction is 0.014% on a fall of 0.718%, about 2% of the linear result, and the two approximations are almost equal. For the large change, the correction is 1.40% on a fall of 7.18%, about 20% of the linear result. The linear approximation overstates the fall in price by almost a quarter of the true fall. This is the reason why the convexity can be ignored for small changes but not for large ones.

The graph below shows the two approximations for the same bond ($D_{Mod}=3.59$, $C=70$). The orange line is the linear approximation. The blue curve is the second-order approximation. The two dots on each line mark the two examples above. Near $\Delta y=0$ the line and the curve are almost equal. As $\Delta y$ grows, the curve bends up and moves away from the line. The gap between them is the convexity term.

![Linear and second-order approximations of the relative price change](Attachments/duration-convexity-approximation.svg)

**Derivation**

The second derivative is the derivative of the first derivative that we computed above:

$$\frac{\mathrm{d}^2P}{\mathrm{d}y^2}=\frac{\mathrm{d}}{\mathrm{d}y}\sum_{t=1}^{n} -t \frac{CF_t}{(1+y)^{t + 1}}$$

We use the same substitution $u = 1 + y$. The first derivative in terms of $u$ is:

$$\frac{\mathrm{d}P}{\mathrm{d}y} = \sum_{t=1}^{n} -t  CF_t  u^{-(t+1)}$$

By the chain rule, and because $\frac{\mathrm{d}u}{\mathrm{d}y}=1$:

$$\frac{\mathrm{d}^2P}{\mathrm{d}y^2} = \left[\frac{\mathrm{d}}{\mathrm{d}u}\sum_{t=1}^{n} -t  CF_t  u^{-(t+1)}\right]\frac{\mathrm{d}u}{\mathrm{d}y} = \frac{\mathrm{d}}{\mathrm{d}u}\sum_{t=1}^{n} -t  CF_t  u^{-(t+1)}$$

Applying the power rule:

$$\frac{\mathrm{d}}{\mathrm{d}u}\sum_{t=1}^{n} -t  CF_t  u^{-(t+1)} = \sum_{t=1}^{n} (-t) CF_t  \big(-(t+1)\big) u^{-(t+2)} = \sum_{t=1}^{n} t(t+1) CF_t  u^{-(t+2)}$$

Substituting back $u = 1 + y$:

$$\frac{\mathrm{d}^2P}{\mathrm{d}y^2} = \sum_{t=1}^{n} \frac{t(t+1) CF_t}{(1+y)^{t+2}}$$

Therefore:

$$C = \frac{1}{P}\frac{\mathrm{d}^2P}{\mathrm{d}y^2} = \frac{1}{P}\sum_{t=1}^{n} \frac{t(t+1) CF_t}{(1+y)^{t+2}}$$

Every term of the sum is positive, because $t$, $CF_t$, and $(1+y)$ are positive. This is the reason why the convexity of a bond with fixed positive cash flows is always positive.

## Practical Interpretation of Durations and Convexity

The modified duration and the convexity are widely used to evaluate the profit and loss (PnL) of a portfolio of fixed-income securities against changes in the interest rates. They approximate how the price of the portfolio changes when the interest rates move. The duration and the convexity of the portfolio are the value-weighted averages of the durations and convexities of its assets. With these two numbers, the two-term formula gives the change in the price of the whole portfolio, without the need to recompute the discounted value of all the cash flows of all the assets. The result is an approximation, and it assumes that all yields move by the same amount (a parallel shift of the yield curve).

**Sensitivity factors**

Three characteristics of a bond determine how sensitive its price is to changes in the interest rates:

- **Maturity:** a longer maturity gives a more sensitive price. The cash flows are further away, so a change in the yield discounts them more.
- **Coupon:** a lower coupon gives a more sensitive price. A larger part of the price comes from the final payment, so the duration is longer. A zero-coupon bond is the most sensitive for a given maturity.
- **Yield:** a lower yield gives a more sensitive price. At a low yield, the discount factors decrease more slowly with time, so the late cash flows carry more weight.

## Key Rate Duration

The duration and the convexity give us a way to estimate the sensitivity of our fixed-income securities to a change in the interest rates. However, we did not define which interest rate changes. The interest rates are not a single number they form a curve, with one rate for each maturity (the yield curve). The rates at different points of this curve can move in different ways. For example, the rate at 10 years can rise while the rate at 1 year falls. The duration and the convexity assume a parallel shift, where all the rates move by the same amount. The key rate duration removes this assumption.

The key rate duration measures the sensitivity of the price of a fixed-income security to a change in the rate at one specific maturity, while all the other rates of the curve stay constant. This is a theoretical construction, in the market, the rates at nearby maturities rarely move in isolation.

**Calculation**

The key rate duration for the maturity $i$ is:

$$KRD_i=-\frac{\Delta P/P}{\Delta y_i}$$

- $\Delta y_i$ is the change in the rate at the maturity $i$, while all the other rates of the curve stay constant.
- $\Delta P/P$ is the percentage change in the price of the security that this change in the rate produces.

The key rate durations of a security add up to its modified duration. If all the rates move by the same amount $\Delta y$, the sum of the effects of each key rate is the effect of a parallel shift:

$$\sum_{i} KRD_i = D_{Mod}$$

> [!NOTE]
> **Why the key rate durations add up to the duration**
>
> The equality is approximate for two reasons. First, each key rate duration is computed with a finite shift, so the second-order terms (convexity) do not cancel exactly. Second, the key rate durations measure shifts of the spot curve, while the modified duration measures a shift of the yield to maturity of the fixed-income security. The sum is therefore the effective duration for a parallel shift. For a plain fixed-income security, this number is very close to the modified duration, and most texts treat them as equal.


**Why it is important**

- **Non-parallel curve:** the yields do not move by the same amount at all maturities. The curve can steepen, flatten, or twist. The modified duration cannot capture these movements.
- **Specific risk:** the key rate durations show the exposure of the portfolio by segment of the curve. A manager can see, for example, that the portfolio is exposed to the 10-year rate but not to the 2-year rate.
- **Precise hedging:** with the exposure by segment, a manager can hedge each segment with an instrument of the same maturity. The hedge is more effective than a hedge based on the total duration only.


**Example**

A 10-year bond has the following key rate durations, computed at three points of the yield curve:

| Maturity | $KRD_i$ |
| :------: | :-----: |
| 2 years  |   0.3   |
| 5 years  |   2.1   |
| 10 years |   5.2   |

The bond is most sensitive to changes in the 10-year rate ($KRD=5.2$) and moderately sensitive to changes in the 5-year rate ($KRD=2.1$). It is almost insensitive to the 2-year rate ($KRD=0.3$). The sum of the three key rate durations, 7.6, is the modified duration of the bond.

If the 10-year rate rises by 0.5% ($\Delta y_{10}=0.005$) and the other rates stay constant, the price falls by approximately:

$\Delta P/P \approx -KRD_{10}\cdot\Delta y_{10} = -5.2\times0.005 = -0.026$, that is a fall of 2.6%.

For a non-parallel movement, we add the effect of each key rate. If the 2-year rate rises by 1%, the 5-year rate rises by 0.5%, and the 10-year rate falls by 0.2%, the price changes by approximately:

$\Delta P/P \approx -(0.3\times0.01) - (2.1\times0.005) - (5.2\times(-0.002)) = -0.0030 - 0.0105 + 0.0104 = -0.0031$, that is a fall of 0.31%.

The modified duration alone cannot compute this result, because the rates did not move by the same amount.

## Asset Swaps

An asset swap is a strategy that combines the purchase of a fixed-coupon bond with the entry into an Interest Rate Swap (IRS). The investor pays the fixed coupons to the swap counterparty and receives floating payments in exchange. The swap transforms the fixed cash flows of the bond into floating cash flows. 

When we buy a bond, this bond usually has a fixed coupon (e.g. 5% every year). Sometimes, instead of a fixed coupon rate, we want exposure to the floating interest rate paid at that moment.

Asset swaps are widely used in fixed income trading strategies to hedge interest rate risk. The swap removes most of the sensitivity of the position to changes in interest rates, but the investor keeps the credit risk of the bond issuer. For this reason, the asset swap spread is a common measure of the credit risk of a bond.

### Mechanics of the Asset Swap

1. **Purchase of the bond:** the investor pays the market price of the bond.
2. **Entry into the IRS:**
   - Pays: the fixed rate of the swap.
   - Receives: the floating rate (EURIBOR/SOFR + spread).
3. **Net cash flows:** pure floating exposure.

### Asset Swap Spread

$$\text{ASW Spread} = (\text{Bond Coupon} - \text{Swap Rate}) \times \frac{100}{\text{Bond Price}}$$

**Interpretation:** the ASW spread is the additional spread over the floating reference rate that the investor receives for the credit risk.


**Example**

Corporate bond XYZ:

- Coupon: 6.5% per year.
- Price: 104.
- Maturity: 5 years.

Market:

- 5-year swap rate: 4.2%.
- 5-year government bond yield: 3.8%.

ASW spread calculation, with the rates in percent:

$\text{ASW} = (6.5 - 4.2) \times (100/104) = 2.3 \times 0.962 = 2.21$%

Comparison:

- Credit spread over the government bond: 6.5% - 3.8% = 2.7%.
- ASW spread: 2.21%.
- Difference: 49 bp, because the bond price is above par.

### Asset Swap Applications

**Why this is interesting**

A fixed-rate bond packages two risks: interest rate risk and credit risk. The asset swap separates them. The investor keeps the credit risk of the issuer and passes the interest rate risk to the swap counterparty. The position behaves like a floating-rate note issued by XYZ.

- **Pure credit view.** If the investor thinks the credit of XYZ is cheap, the asset swap pays only for that view. A rate move does not change the result.
- **Comparable numbers.** The ASW spread puts every bond on one scale: spread over the swap curve. A 3-year bond at 98 and a 7-year bond at 105 become directly comparable.
- **Access to fixed-rate supply.** Most corporate bonds are fixed-rate, but many investors need floating cash flows. The asset swap converts the available supply into the required form.
- **Floating-rate funding.** A bank funds itself at a floating rate. It buys the bond, swaps it, and locks the margin between "floating + ASW spread" and its floating funding cost.
- **Relative value.** If the ASW spread is wider than the CDS spread of the same issuer, the investor can buy the bond, swap it, and buy protection. This is the CDS-bond basis trade.

**When this is not interesting**

- **The investor wants duration.** If the investor expects rates to fall, the swap removes the price gain that the investor wants.
- **Costs are high relative to the spread.** The swap bid-offer, the collateral requirements, and the counterparty risk can consume a small ASW spread.
- **The bond has embedded options.** A callable or puttable bond does not have certain fixed cash flows. A standard asset swap does not hedge it well.
- **Rates are stable.** The value of the duration hedge is low when rate uncertainty is low. The swap then adds cost with little benefit.

**Practical applications**

- **Relative value analysis.** Compare the ASW spreads of different issuers with the same maturity. A wider spread means more compensation per unit of credit risk.
- **Bond vs. CDS arbitrage.** If the ASW spread is greater than the CDS spread of the same issuer, buy the bond, swap it, and buy protection. The position earns the difference with little net credit risk.
- **Sector rotation.** Compare the average ASW spread of each sector against its history. Identify sectors that are cheap or expensive relative to their usual level.
- **Portfolio construction.** Use asset-swapped bonds as the base of a credit-neutral portfolio. The portfolio then has credit exposure only, with no duration exposure.

## Appendix 1: Taylor Polynomial and the Relative Price Change

A Taylor polynomial replaces a complicated function with a simple polynomial that behaves like the function near one chosen point. At that point, the polynomial has the same value, the same slope, the same curvature, and so on, up to the degree that we choose. The more derivatives that match, the further from the point the polynomial stays close to the function.

**Why we need it for the price of a fixed-income security**

The price of any fixed-income security with fixed cash flows is $P(y)=\sum_{t} CF_t (1+y)^{-t}$. The formula can be computed exactly for any yield. The difficulty is the price change. Note that the derivatives give us infinitesimal changes. Nonetheless, the exact relative change for a finite yield move needs two points of the price curve: the current price at $y_0$ and the new price at $y_0+\Delta y$. Therefore, the relative price variation for a specific yield variation is expressed as:

$$
\begin{aligned}
\frac{\Delta P}{P}
&= \frac{P(y_1)-P(y_0)}{P(y_0)} \\
&= \frac{\displaystyle\sum_{t} CF_t (1+y_1)^{-t} - \displaystyle\sum_{t} CF_t (1+y_0)^{-t}}{\displaystyle\sum_{t} CF_t (1+y_0)^{-t}} \\
&= \frac{\displaystyle\sum_{t} CF_t (1+y_1)^{-t}}{\displaystyle\sum_{t} CF_t (1+y_0)^{-t}} - 1
\end{aligned}
$$

The yield change is $\Delta y = y_1 - y_0$, then $y_1 = y_0 + \Delta y$ and:

$$
\frac{\Delta P}{P} = \frac{\displaystyle\sum_{t} CF_t (1+y_0+\Delta y)^{-t}}{\displaystyle\sum_{t} CF_t (1+y_0)^{-t}} - 1
$$

This expression is exact, but it has three practical problems:

- **No simple form in $\Delta y$.** The numerator is a sum of $n$ terms, each with a different power of $(1+y_0+\Delta y)$. No factorization removes the sum, so the expression does not reduce to a short polynomial like $a + b \Delta y + c \Delta y^2$. The denominator is also a sum of powers, but it does not contain $\Delta y$: it is the current price $P(y_0)$, a single constant.
- **No separation between the security and the shock.** The cash flows $CF_t$, the yield $y_0$, and the shock $\Delta y$ are mixed inside the same powers. It is not possible to compute a number that describes the security once, and then apply any $\Delta y$ to it later. Each new $\Delta y$ requires a full repricing of every cash flow.
- **No portfolio summary.** The change of a portfolio is the sum of the changes of its securities, so it is additive. But there is no single number that describes the sensitivity of the whole portfolio. Each security must be repriced on its own, and the results added.

The differential $\mathrm{d}P = P'(y) \mathrm{d}y$ is exact and simple, but only for an infinitely small $\mathrm{d}y$. The Taylor polynomial connects the two. The expansion point is the current yield $y_0$, so the polynomial is built around the price $P(y_0)$ before the interest rate changes. It expresses the finite change with a few numbers ($D_{Mod}$, $C$) that are computed once at the current yield, are simple functions of $\Delta y$, and aggregate across a portfolio as weighted averages.

The $n$-th degree Taylor polynomial of a function $f(x)$ centered at $x=a$ is:

$$P_{n}(x)=\sum _{k=0}^{n}\frac{f^{(k)}(a)}{k!}(x-a)^{k}$$

The factor $1/k!$ appears because the $k$-th derivative of $(x-a)^k$ is $k!$. It cancels, so the $k$-th derivative of $P_n$ at $a$ equals $f^{(k)}(a)$. If we stop at degree $n$, the error is proportional to $(x-a)^{n+1}$, which is small when $x$ is close to $a$.

**Application to the price of a fixed-income security**

Here the function is the price $P(y)$ of the security, the point is the current yield $y_0$, and the distance from the point is the yield change $\Delta y = y - y_0$. The second-degree Taylor polynomial gives:

$$P(y_0+\Delta y) = P(y_1) \approx P(y_0) + P'(y_0) \Delta y + \frac{1}{2}P''(y_0) (\Delta y)^2$$

We want the relative variation of the price, not the new price. We move $P(y_0)$ to the left side and divide by $P(y_0)$:

$$\frac{\Delta P}{P} = \frac{P(y_1)-P(y_0)}{P(y_0)} \approx \frac{P'(y_0)}{P(y_0)} \Delta y + \frac{1}{2} \frac{P''(y_0)}{P(y_0)} (\Delta y)^2$$

The two ratios are the modified duration and the convexity:

$$D_{Mod} = -\frac{P'(y_0)}{P(y_0)} \qquad C = \frac{P''(y_0)}{P(y_0)}$$

So the relative price change is:

$$\frac{\Delta P}{P} \approx -D_{Mod} \Delta y + \frac{1}{2} C (\Delta y)^2$$

The [Modified Duration](#modified-duration) formula keeps only the first-degree term. It follows the tangent line. The [Convexity](#convexity) formula adds the second-degree term. It follows a parabola that bends like the price curve. The dropped terms are proportional to $(\Delta y)^3$ and higher. For a yield move of 100 bp, $(\Delta y)^3 = 10^{-6}$, so two terms are enough for normal market moves.

TODO: Modify this page adding also the calculations for the continuous capitalization