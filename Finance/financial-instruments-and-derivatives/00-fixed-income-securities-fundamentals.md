# Fixed Income Securities Fundamentals

## Core fixed-income securities

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

A certificate of deposit (CD) is different. The client agrees to leave a fixed amount in the bank until a maturity date (e.g. 3 months, 6 months, or 1 year). In exchange, the bank pays a fixed interest rate, usually higher than the rate on a demand deposit. If the client withdraws the money before maturity, the bank applies a penalty. Because the cash flows are fixed in advance, a CD is a fixed-income security, like a bond or a bill.

The main problem of a CD is its limited liquidity. Unlike bonds and bills, a CD is a contract between the client and one bank, and there is no market where the client can easily resell this debt to another investor. The only way to recover the money before maturity is to pay the penalty to the bank. Only large CDs issued to institutions (negotiable CDs) can be sold in a secondary market.

## Macaulay Duration

The Macaulay duration is the average time, in years, at which an investor receives the cash flows of a fixed-income security. Each cash flow is weighted by its present value. The formula is:

$$D_{Mac}=\frac{1}{P}\sum_{t=1}^{n} t \cdot \frac{CF_t}{(1+y)^t}$$

- $t$ is the time of each cash flow, in years.
- $n$ is the number of cash flows.
- $CF_t$ is the cash flow paid at time $t$ (coupon, or coupon plus principal at maturity).
- $P$ is the price of the security.
- $y$ is the yield to maturity. It is the discount rate that makes the sum of the discounted cash flows equal to $P$.

The formula sums all the cash flows, each multiplied by the time at which it is paid and discounted at the yield to maturity with compound interest. The sum is then divided by the price of the security. The division by $P$ is what turns the sum into an average. A weighted average of the times $t$ is the sum of each $t$ multiplied by a weight, where all the weights add up to 1. In the formula, the weight of each time $t$ is its discounted cash flow divided by $P$. Because $y$ is the rate that makes the discounted cash flows add up to the price:

$$\sum_{t=1}^{n} \frac{CF_t}{(1+y)^t} = P$$

the weights add up to exactly 1, and $D_{Mac}$ is a true average of the times $t$. Each time $t$ counts in proportion to the share of the price that its cash flow represents. A cash flow that is large or paid soon has a large present value and pulls the average towards its time. A cash flow that is small or paid late has a small present value and pulls the average less.

A zero-coupon bond is the simplest check. It has one cash flow at maturity, so that cash flow is the whole price, its weight is 1, and the Macaulay duration equals the maturity. A coupon bond pays part of the price before maturity, so its Macaulay duration is shorter than the maturity.

**Example**

A bond has a face value of 100 and a maturity of 4 years. It pays an annual coupon of 5%. The yield to maturity (YTM) is 4%.

| Year ($t$) | Cash flow ($CF_t$) | Present value of the cash flow ($PV_t$) | $t \times PV_t$ |
| :--------: | :----------------: | :-------------------------------------: | :--------------: |
|     1      |         5          |                  4.80                   |       4.80       |
|     2      |         5          |                  4.622                  |      9.244       |
|     3      |         5          |                  4.444                  |      13.332      |
|     4      |        105         |                  89.75                  |       359        |
| **Total**  |                    |                 103.616                 |     386.376      |

$$D_{Mac}=3.73$$


## Modified Duration

The Modified Duration measures the sensitivity of the price of the security when there are changes in the interest rates. When the yield rises, the price of a fixed-income security falls. The modified duration measures how much: it is the percentage change in price for a change of 1 unit (100%) in the yield. It is the Macaulay duration divided by $(1 + y)$:

$$D_{Mod}=\frac{D_{Mac}}{1+y}$$

- $D_{Mac}$ is the Macaulay duration, in years.
- $y$ is the yield to maturity.

With the modified duration, the percentage change in price for a small change in yield is:

$$\frac{\Delta P}{P}\approx -D_{Mod}\times\Delta y$$

- $\Delta y$ is the change in the yield (e.g. $0.01$ for a rise from 4% to 5%).
- $\Delta P / P$ is the percentage change in the price.
- The minus sign shows that the price moves in the opposite direction to the yield.

> [!note] Why is this an approximation?
> The derivation below gives an exact result, but only for an infinitely small change in yield: $\frac{1}{P}\frac{\mathrm{d}P}{\mathrm{d}y} = -D_{Mod}$. This is the slope of the price curve at the current yield. The formula above replaces the infinitely small change $\mathrm{d}y$ with a finite change $\Delta y$, so it follows the straight line with that slope instead of the curve. The price curve is convex (it bends upwards), and the line is below the curve everywhere except at the current yield. For a small $\Delta y$ the gap is negligible. For a large $\Delta y$ the gap grows, and the true fall in price is smaller than the formula predicts. In Taylor expansion terms, the formula keeps only the first-order term and drops the convexity term, which is proportional to $(\Delta y)^2$.

The two durations measure different things. The Macaulay duration is a time, in years. The modified duration is a sensitivity of the price to the yield. The division by $(1 + y)$ converts the time into the sensitivity.

**Example**

The bond above has $D_{Mac}=3.73$ and $y=4\%$, so $D_{Mod}=3.73/1.04=3.59$. If the yield rises by 1% (from 4% to 5%), the price falls by approximately $\Delta P/P \approx -D_{Mod} \times \Delta y = -3.59 \times 0.01 = -3.59\%$. The approximation is a first-order one. For large changes in yield, the convexity of the price curve makes the true fall smaller and the true rise larger.

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

## Convexity

As we saw, the modified duration is a linear approximation. If the change in the yield is large, this approximation becomes unreliable, because the price curve is convex, not a straight line. Convexity is the second-order term that corrects this error.

The convexity measures the curvature of the price-yield curve. It improves the approximation by adding a second-order term to the formula. The convexity is the second derivative of the price with respect to the yield, divided by the price:

$$C=\frac{1}{P}\frac{d^2P}{dy^2}=\frac{1}{P}\sum_{t=1}^{n} \frac{t(t+1) \cdot CF_t}{(1+y)^{t+2}}$$

With this term, the second-order approximation of the price change is:

$$\frac{\Delta P}{P} \approx -D_{Mod} \cdot \Delta y + \frac{1}{2} C \cdot (\Delta y)^2$$

> [!note]
> This formula is a second-order Taylor polynomial of the price around the current yield. The first-order term is the duration. The second-order term is the convexity. The formula ignores the terms of order three and higher, so it is still an approximation.

In most cases the convexity is positive. A positive convexity always gives a better result than the simpler linear approximation, whatever the interest rates do. If the interest rates rise, the convexity term reduces the fall in price that the linear approximation computes. If the interest rates fall, the convexity term increases the rise in price that the linear approximation computes.

The effect of the convexity is small for small changes in the interest rates. It becomes important for large changes, for example when a long period of time has passed and the interest rates have moved far from their initial level.

**Example**

We continue with the bond above: $D_{Mod}=3.59$ and $y=4\%$. We take a convexity of $C=70$ to make the effect visible.

For a small change, $\Delta y=0.002$:

$$\text{Linear: } -D_{Mod}\cdot\Delta y = -3.59\times0.002 = -0.718\%$$
$$\text{Convexity term: } \tfrac{1}{2}C\cdot(\Delta y)^2 = \tfrac{1}{2}\times70\times0.002^2 = +0.014\%$$
$$\text{Second order: } -0.718\% + 0.014\% = -0.704\%$$

For a large change, $\Delta y=0.02$:

$$\text{Linear: } -D_{Mod}\cdot\Delta y = -3.59\times0.02 = -7.18\%$$
$$\text{Convexity term: } \tfrac{1}{2}C\cdot(\Delta y)^2 = \tfrac{1}{2}\times70\times0.02^2 = +1.40\%$$
$$\text{Second order: } -7.18\% + 1.40\% = -5.78\%$$

| Change in yield | Linear approximation | Convexity term | Second-order approximation |
| :-------------: | :------------------: | :------------: | :------------------------: |
|     +0.2%       |       -0.718%        |    +0.014%     |          -0.704%           |
|     +2%         |       -7.18%         |    +1.40%      |          -5.78%            |

The linear term grows in proportion to $\Delta y$. The convexity term grows in proportion to $(\Delta y)^2$. The change in yield is 10 times larger, so the linear term is 10 times larger, but the convexity term is 100 times larger. For the small change, the correction is 0.014% on a fall of 0.718%, about 2% of the linear result, and the two approximations are almost equal. For the large change, the correction is 1.40% on a fall of 7.18%, about 20% of the linear result. The linear approximation overstates the fall in price by almost a quarter of the true fall. This is the reason why the convexity can be ignored for small changes but not for large ones.

**Derivation**

TODO: Derivate 

## Practical Intuition

The modified duration and the convexity are widely used to evaluate the profit and loss (PnL) of a portfolio of fixed-income securities against changes in the interest rates. They approximate how the price of the portfolio changes when the interest rates move. The duration and the convexity of the portfolio are the value-weighted averages of the durations and convexities of its assets. With these two numbers, the two-term formula gives the change in the price of the whole portfolio, without the need to recompute the discounted value of all the cash flows of all the assets. The result is an approximation, and it assumes that all yields move by the same amount (a parallel shift of the yield curve).

**Sensitivity factors**

Three characteristics of a bond determine how sensitive its price is to changes in the interest rates:

- **Maturity:** a longer maturity gives a more sensitive price. The cash flows are further away, so a change in the yield discounts them more.
- **Coupon:** a lower coupon gives a more sensitive price. A larger part of the price comes from the final payment, so the duration is longer. A zero-coupon bond is the most sensitive for a given maturity.
- **Yield:** a lower yield gives a more sensitive price. At a low yield, the discount factors decrease more slowly with time, so the late cash flows carry more weight.

