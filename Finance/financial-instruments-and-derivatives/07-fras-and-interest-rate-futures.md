# FRAs and Interest Rate Futures

## Forward Rate Agreements

A forward rate agreement (FRA) is an over-the-counter agreement to exchange a fixed rate $R_K$ for a reference rate that the market will observe in the future. Both rates apply to a principal $L$ for the period from $t_1$ to $t_2$, of $\tau = t_2 - t_1$ years, but the principal is not exchanged. The reference rate was usually LIBOR. After its phase-out, FRAs use rates such as three-month SOFR or SONIA (see [Interest Rates](01-interest-rates.md)).

An FRA locks in a future rate. A trader who will receive SOFR on a principal in a future period receives a fixed rate and pays SOFR in an FRA. A trader who will pay SOFR does the opposite.

As OTC contracts, FRAs can have any notional, dates, and reference rate. Most use standard periods such as $3 \times 6$ and $6 \times 12$ and standard documentation (FRABBA terms, ISDA definitions), because standard contracts are easier to price, hedge, and close.

### Payoff

If $R_M$ is the reference rate that the market observes for the period, the party that receives the fixed rate gets the following amount at $t_2$. A negative amount goes to the other party.

$$\text{Payoff}_{\text{receive fixed}} = L \tau (R_K - R_M)$$

**Example.** An FRA exchanges 3% for three-month LIBOR from year 2 to year 2.25 on a principal of \$100 million, with quarterly compounding. LIBOR proves to be 3.5%, so the party that pays 3% and receives LIBOR gets

$$100{,}000{,}000 \times (0.035 - 0.030) \times 0.25 = \$125{,}000$$

at 2.25 years. In practice, LIBOR is known at year 2, so the payment is made at 2 years and is $125{,}000 / (1 + 0.035 \times 0.25) = \$123{,}916$.

### Valuation

When an FRA is set up, $R_K$ is normally the forward rate $R_F$ of the reference rate for the period (see [Interest Rate Curves](02-interest-rates-curves.md)), so the FRA is worth zero. Later $R_F$ changes. A new FRA at $R_F$ is worth zero, and for the party that receives the fixed rate it differs from the old FRA only by $L \tau (R_K - R_F)$ at $t_2$. The old FRA is thus worth the present value of this amount.

$$V_{\text{receive fixed}} = L \tau (R_K - R_F) DF(t_2) \qquad V_{\text{pay fixed}} = L \tau (R_F - R_K) DF(t_2)$$

An FRA can thus be valued if we assume that the reference rate will equal today's forward rate $R_F$. $R_K$ and $R_F$ use the compounding of the period.

### Backward Looking vs Forward Looking

A forward-looking rate is fixed at the start of its period. LIBOR, now phased out (see [Interest Rates](01-interest-rates.md)), was such a rate, and EURIBOR still is. In an FRA on LIBOR, $R_M$ was known at $t_1$, so the FRA settled at $t_1$ with the payoff discounted from $t_2$ to $t_1$ at $R_M$.

A backward-looking rate is known only at the end of its period. SOFR is an overnight rate, so the FRA uses SOFR compounded day by day over the period, from actual overnight repo transactions. $R_M$ is thus known only at $t_2$, and the FRA pays the payoff at $t_2$ with no discount. Term SOFR, a forward-looking rate derived from SOFR futures, can restore the old structure, but US market guidance limits its use in derivatives to hedges of Term SOFR loans.

![Timeline of the payment of an FRA on LIBOR and on SOFR](Attachments/fra-libor-vs-sofr-timeline.svg)

## Liquidity Preference Theory

Explain what liquidity preference theory and expectations theory imply about forward rates and expected future rates.

**Expectations theory:** Investors care only about expected returns, so the forward rate equals the expected future spot rate. Forward rates are unbiased predictors, and the yield curve's slope reflects only expected rate changes. An upward slope means rates are expected to rise.

**Liquidity preference theory:** Investors demand a premium for holding riskier long-term bonds, so the forward rate equals the expected future spot rate plus a liquidity premium. Forward rates therefore overstate expected future spot rates. This is why the curve usually slopes upward even when rates are expected to stay flat.

**Example:** With a 1-year spot of 4% and a 2-year spot of 5%, the forward rate is about 6%. Expectations theory says the market expects next year's rate to be 6%. Liquidity preference theory, with a 1% premium, says it expects about 5%.
