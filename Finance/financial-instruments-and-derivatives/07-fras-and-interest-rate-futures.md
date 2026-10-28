# FRAs and Interest Rate Futures

## Forward Rate Agreements

A forward rate agreement (FRA) is an over-the-counter contract that fixes today an interest rate $R_K$ on a notional $N$ for one future period $[t_1, t_2]$ of $\tau$ years. The floating side is a term reference rate that fixes at the start of the period, such as 3-month EURIBOR. An overnight rate such as SOFR does not fit, because its compounded value is known only at the end of the period (see [Interest Rates](01-interest-rates.md)). The parties never exchange the notional, only the difference in interest, discounted to $t_1$. The buyer pays $R_K$ and gains if rates rise. The seller receives $R_K$ and gains if rates fall.

As OTC contracts, FRAs can have any notional, dates, and reference rate. Most use standard periods such as $3 \times 6$ and $6 \times 12$ and standard documentation (FRABBA terms, ISDA definitions), because standard contracts are easier to price, hedge, and close.

### Notation

An $A \times B$ FRA covers the period from month $A$ to month $B$. For example, a $3 \times 6$ FRA fixes the 3-month rate that starts in 3 months, so $\tau \approx 0.25$.

### FRA Rate

The FRA rate is the forward rate $F$ of the reference rate for $[t_1, t_2]$, with simple compounding (see [Interest Rate Curves](02-interest-rates-curves.md)). It is the no-arbitrage rate of today's curve, not a forecast of the future rate.

$$F = \frac{1}{\tau} \left[ \frac{DF(t_1)}{DF(t_2)} - 1 \right]$$

In this formula, $\tau$ is the year fraction from $t_1$ to $t_2$ in the day count of the reference rate (ACT/360 for EURIBOR). At the start, the parties set $R_K = F$, so the FRA is worth zero.

### Settlement

The reference rate $R$ fixes two business days before $t_1$ for EURIBOR, and the FRA settles in cash at $t_1$. The difference in interest is due at $t_2$, so the settlement discounts it to $t_1$ at $R$.

$$\text{Settlement}_{buyer} = \frac{N \tau (R - R_K)}{1 + \tau R}$$

A positive amount goes from the seller to the buyer, and a negative amount from the buyer to the seller.

### Valuation

After the start, $R_K$ stays fixed while $F$ moves with the curve, so the FRA gains or loses value. The value assumes that $R$ will equal $F$ and discounts the difference in interest from $t_2$.

$$V_{buyer} = N \tau (F - R_K) DF(t_2) \qquad V_{seller} = -V_{buyer}$$

Since the credit crisis of 2007, the discount factors in $F$ come from a separate curve of the reference rate, and for a collateralized FRA $DF(t_2)$ comes from the OIS curve (see [Interest Rates](01-interest-rates.md)). The two curves differ because EURIBOR includes a premium for the credit and liquidity risk of banks.



## Liquidity Preference Theory

Explain what liquidity preference theory and expectations theory imply about forward rates and expected future rates.

**Expectations theory:** Investors care only about expected returns, so the forward rate equals the expected future spot rate. Forward rates are unbiased predictors, and the yield curve's slope reflects only expected rate changes. An upward slope means rates are expected to rise.

**Liquidity preference theory:** Investors demand a premium for holding riskier long-term bonds, so the forward rate equals the expected future spot rate plus a liquidity premium. Forward rates therefore overstate expected future spot rates. This is why the curve usually slopes upward even when rates are expected to stay flat.

**Example:** With a 1-year spot of 4% and a 2-year spot of 5%, the forward rate is about 6%. Expectations theory says the market expects next year's rate to be 6%. Liquidity preference theory, with a 1% premium, says it expects about 5%.
