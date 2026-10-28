# FRAs and Interest Rate Futures

## Forward Rates Agreements

A forward rate agreement (FRA) is an over-the-counter contract in which two parties agree today on a fixed interest rate to be applied to a notional principal for a single specified period in the future. At settlement, usually at the start of that period, they exchange only the net difference between the fixed rate and the floating reference rate (such as SOFR or EURIBOR), applied to the notional and discounted. The notional itself is never exchanged. An FRA is valued using today's yield curve: first, the forward rate for the contract period is derived from current discount factors as F = (P(T₁)/P(T₂) − 1)/τ, where τ is the length of the period. Then, assuming this forward rate will be realized, the value for the party receiving the fixed rate R_K is V = N × (R_K − F) × τ × P(T₂), with the sign reversed for the fixed-rate payer. The forward rate is not simply the market's expectation of future rates but the arbitrage-free rate implied by today's curve, which is why an FRA has zero value at inception (when R_K = F) and gains or loses value as interest rates move.

Because FRAs are OTC contracts, the two parties can customize all the terms, such as the notional, the dates, and the reference rate. In practice, most FRAs use standard terms, such as common periods ($3 \times 6$, $6 \times 12$) and standard legal documentation, because standard contracts are easier to price, hedge, and close.

### Notation

An FRA $A \times B$ covers the period that starts in $A$ months and ends in $B$ months. For example, a $3 \times 6$ FRA fixes the interest rate for the 3-month period that starts in 3 months, so $\tau = 0.25$.

### FRA Rate

The FRA rate is the forward rate for the period $[t_1, t_2]$, which comes from the discount factors of today.

$$F_{FRA}(t_1, t_2) = \frac{1}{\tau} \left[ \frac{DF(t_1)}{DF(t_2)} - 1 \right]$$

In this formula, $\tau = t_2 - t_1$ is the length of the period in years.

### Settlement

The FRA settles at $t_1$, when the reference rate fixes. The interest for the period is paid at $t_2$, so the settlement discounts the difference in interest from $t_2$ back to $t_1$ with the reference rate that fixes at $t_1$.

$$\text{Settlement} = \frac{N \times \tau \times (R_{fixing} - F_{FRA})}{1 + \tau \times R_{fixing}}$$

In this formula, $N$ is the notional and $R_{fixing}$ is the reference rate that fixes at $t_1$. If the settlement is positive, the buyer of the FRA, who pays the fixed rate, receives it from the seller. If the settlement is negative, the buyer pays it to the seller.




## Liquidity Preference Theory

Explain what liquidity preference theory and expectations theory imply about forward rates and expected future rates.

**Expectations theory:** Investors care only about expected returns, so the forward rate equals the expected future spot rate. Forward rates are unbiased predictors, and the yield curve's slope reflects only expected rate changes. An upward slope means rates are expected to rise.

**Liquidity preference theory:** Investors demand a premium for holding riskier long-term bonds, so the forward rate equals the expected future spot rate plus a liquidity premium. Forward rates therefore overstate expected future spot rates. This is why the curve usually slopes upward even when rates are expected to stay flat.

**Example:** With a 1-year spot of 4% and a 2-year spot of 5%, the forward rate is about 6%. Expectations theory says the market expects next year's rate to be 6%. Liquidity preference theory, with a 1% premium, says it expects about 5%.