# Non-standard Swaps

## European Swaptions

Swap options, or swaptions, are popular interest rate options that give the holder the right to enter a specified interest rate swap at a specified future date. The swaptions below are European, so the holder can exercise them only on the expiry date.

A swap is equivalent to the exchange of a fixed-rate bond for a floating-rate bond, which is worth its principal at the start of the swap. A swaption is therefore an option on the fixed-rate bond, with a coupon equal to the strike swap rate and a strike price equal to the principal.

| Swaption | Right of the holder | Option on the swap rate | Option on the fixed-rate bond | Gains when rates |
|---|---|---|---|---|
| Payer | Pay fixed, receive floating | Call | Put | Rise |
| Receiver | Receive fixed, pay floating | Put | Call | Fall |

The market names a swaption by the expiry of the option followed by the tenor of the swap. For example, a 2Y5Y payer is a 2-year option to enter a 5-year payer swap that starts in 2 years.

A company that will take a floating-rate loan and swap it to fixed can buy a payer swaption to set a maximum on that fixed rate. A forward swap locks in the fixed rate with no up-front cost, but it obliges the company to enter the swap. The swaption costs a premium, but if rates fall, the company lets it expire and enters a swap at the lower market rate.

Compared with a new swap at the market rate, which has the same floating leg, the payoff of a swaption on each payment date of the swap is

$$\text{Payer payoff} = \frac{L}{m} \max(s_T - s_K, 0) \qquad \text{Receiver payoff} = \frac{L}{m} \max(s_K - s_T, 0)$$

where

- $L$ is the principal (notional) of the swap.
- $m$ is the number of payments per year, so $L/m$ is the principal times the accrual fraction of one period when day counts are ignored.
- $s_T$ is the swap rate at the expiry $T$, which is the fixed rate of a new swap with the same tenor at that date.
- $s_K$ is the strike swap rate, which is the fixed rate that the holder pays (payer) or receives (receiver) after exercise.

For an $n$-year swap, the holder gets this payoff on the $mn$ payment dates $T_1, \dots, T_{mn}$, in years from today, with $T_i \approx T + i/m$. A swaption is a single option on the swap rate with repeated payoffs.

At the expiry, the $mn$ payoffs are worth $L A_T \max(s_T - s_K, 0)$ (payer) or $L A_T \max(s_K - s_T, 0)$ (receiver). Here $A_t = \frac{1}{m} \sum_{i=1}^{mn} P(t, T_i)$ is the annuity of the swap per unit of principal at time $t$, and $P(t, T_i)$ is the discount factor from $t$ to $T_i$.

Black's model, the standard market model, assumes that $s_T$ is lognormal and gives the values today as

$$V_{\text{payer}} = L A_0 [s_F N(d_1) - s_K N(d_2)] \qquad V_{\text{receiver}} = L A_0 [s_K N(-d_2) - s_F N(-d_1)]$$

$$d_1 = \frac{\ln(s_F/s_K) + \sigma^2 T/2}{\sigma \sqrt{T}} \qquad d_2 = d_1 - \sigma \sqrt{T}$$

where

- $s_F$ is the forward swap rate, which is the fixed rate that gives a zero value today to the swap that starts at $T$.
- $\sigma$ is the volatility of the forward swap rate, so $\sigma \sqrt{T}$ is the standard deviation of $\ln s_T$.
- $N(\cdot)$ is the cumulative distribution function of the standard normal distribution.

Black's model needs positive rates. For rates near or below zero, the market uses the normal (Bachelier) model, with volatilities in basis points, or a shifted lognormal model.



## Interest Rate Caps and Floors

### Caps

An interest rate cap is a series of call options on interest rates, called caplets. It can be understood by considering a floating-rate note where the interest rate is reset every three months. The interest rate of each three-month period is based on a three-month reference interest rate, applicable to the period, that is observed in the market.

Interest rate caps provide protection against rises in the interest rate above a strike rate, called the cap rate $R_K$. A borrower that pays interest on the note and holds a cap pays at most $R_K$ in each period.

For example, a company borrows USD 10 million for five years with the floating-rate note and enters into a cap with a notional principal of USD 10 million and a cap rate of 3% per annum. The effective reference interest rate that determines the loan interest payments is then never more than 3% per annum. If the reference interest rate for a quarter is less than 3%, the cap gives no payoff for that quarter. If the rate is more than 3%, the payoff brings the effective reference interest rate down to 3% per annum. For example, if the reference interest rate for a quarter is 3.5% per annum, the cap gives a payoff at the end of the quarter of

$$10{,}000{,}000 \times 0.25 \times (0.035 - 0.03) = 12{,}500$$

to reduce the effective reference interest rate for the quarter to 3% per annum.

### Floors

An interest rate floor is a series of put options on interest rates, called floorlets. It can be understood by considering the same floating-rate note, but from the side of the investor that holds the note and receives its interest.

Interest rate floors provide protection against falls in the interest rate below a strike rate, called the floor rate $R_K$. An investor that receives interest on the note and holds a floor receives at least $R_K$ in each period.

For example, an investor buys a five-year floating-rate note with a principal of USD 10 million and enters into a floor with a notional principal of USD 10 million and a floor rate of 2% per annum. The effective reference interest rate that determines the interest that the investor receives is then never less than 2% per annum. If the reference interest rate for a quarter is more than 2%, the floor gives no payoff for that quarter. If the rate is less than 2%, the payoff brings the effective reference interest rate up to 2% per annum. For example, if the reference interest rate for a quarter is 1.5% per annum, the floor gives a payoff at the end of the quarter of

$$10{,}000{,}000 \times 0.25 \times (0.02 - 0.015) = 12{,}500$$

to increase the effective reference interest rate for the quarter to 2% per annum.

### Collar

A collar guarantees that the interest rate on an underlying floating-rate note always lies between two levels. It combines a long cap and a short floor, usually with the price of the cap initially equal to the price of the floor, so the collar costs nothing to enter.

This collar suits a borrower that pays the floating rate and wants to hedge the loan at no initial cost, but, unlike with a payer swap, still pay the market rate between the two levels. The long cap protects against rises in rates and the premium of the short floor pays for it, but the borrower gives up the gain from rates below the floor rate. With a reference rate $R$, a cap rate $R_C$, and a floor rate $R_F < R_C$, the effective rate in each period always lies between $R_F$ and $R_C$

$$R_{\text{eff}} = R - \max(R - R_C, 0) + \max(R_F - R, 0)$$

For example, a loan of USD 10 million with quarterly resets has a cap rate of 3% and a floor rate of 2%.

| Reference rate | Cap payoff to the borrower | Floor payoff by the borrower to the floor holder | Effective rate |
|---|---|---|---|
| 3.5% | 12,500 | 0 | 3% (cap rate) |
| 2.5% | 0 | 0 | 2.5% (market rate) |
| 1.5% | 0 | 12,500 | 2% (floor rate) |

An investor that receives the floating rate uses the opposite collar, which is a long floor and a short cap.

### Put-Call Parity for Caps and Floors

The put-call parity relationship between the prices of caps and floors is

$$V_{\text{cap}} = V_{\text{floor}} + V_{\text{swap}}$$

In this relationship, the cap and the floor have the same strike rate $R_K$. The swap is an agreement to receive a floating rate $R$ and pay a fixed rate $R_K$, with no exchange of payments on the first reset date. All three instruments have the same life and the same frequency of payments.

To see that the result is true, consider a long position in the cap combined with a short position in the floor. The cap provides a cash flow of $R - R_K$ for periods when $R$ is greater than $R_K$. The short floor provides a cash flow of $-(R_K - R) = R - R_K$ for periods when $R$ is less than $R_K$. There is therefore a cash flow of $R - R_K$ in all circumstances. This is the cash flow on the swap. It follows that the value of the cap minus the value of the floor must equal the value of the swap.

### Valuation of Caps and Floors

Each caplet and floorlet covers one period from $t_k$ to $t_{k+1}$. The reference interest rate of the period is observed at $t_k$, and the payoff is paid at $t_{k+1}$

$$\text{Caplet payoff} = L \delta_k \max(R_k - R_K, 0) \qquad \text{Floorlet payoff} = L \delta_k \max(R_K - R_k, 0)$$

where

- $L$ is the notional principal.
- $\delta_k = t_{k+1} - t_k$ is the accrual fraction of the period, in years.
- $R_k$ is the reference interest rate for the period, observed at $t_k$.
- $R_K$ is the cap rate or the floor rate.

The rate of the first period is known when the cap or floor starts, so there is usually no caplet or floorlet for that period.

Black's model assumes that each $R_k$ is lognormal and gives the values today as

$$V_{\text{caplet}} = L \delta_k P(0, t_{k+1}) [F_k N(d_1) - R_K N(d_2)] \qquad V_{\text{floorlet}} = L \delta_k P(0, t_{k+1}) [R_K N(-d_2) - F_k N(-d_1)]$$

$$d_1 = \frac{\ln(F_k/R_K) + \sigma_k^2 t_k/2}{\sigma_k \sqrt{t_k}} \qquad d_2 = d_1 - \sigma_k \sqrt{t_k}$$

where

- $F_k$ is the forward rate today for the period from $t_k$ to $t_{k+1}$.
- $\sigma_k$ is the volatility of $F_k$, so $\sigma_k \sqrt{t_k}$ is the standard deviation of $\ln R_k$.
- $P(0, t_{k+1})$ is the discount factor to the payment date $t_{k+1}$, not to the expiry $t_k$.

The value of a cap or a floor is the sum of the values of its caplets or floorlets. The market quotes a cap or a floor with one flat volatility, which is the single $\sigma$ that gives its price when it is used for all of its caplets or floorlets. As for swaptions, the market uses the normal or the shifted lognormal model when rates are near or below zero.

Because $\max(R_k - R_K, 0) - \max(R_K - R_k, 0) = R_k - R_K$, a long cap and a short floor with the same strike rate $R_K$ are equal to a payer swap with the fixed rate $R_K$. So a collar with $R_C = R_F$ is a payer swap, and the cap and the floor have the same price only when $R_K$ is equal to the forward swap rate.

## SABR model

Black's model uses one volatility $\sigma$ for all strikes, but the market prices of swaptions and caps give implied volatilities that change with the strike, which is the volatility smile. The SABR (stochastic alpha, beta, rho) model gives the forward rate a stochastic volatility, so it can fit the smile

$$dF = \alpha F^\beta dW_1 \qquad d\alpha = \nu \alpha dW_2 \qquad dW_1 dW_2 = \rho dt$$

where

- $F$ is the forward rate of the underlying instrument, which is the forward swap rate for a swaption or the forward rate of the period for a caplet.
- $\alpha$ is the volatility of the forward rate, and its initial value $\alpha_0$ sets the level of the volatility.
- $\beta$, from 0 to 1, sets the distribution of the forward rate, which is normal for $\beta = 0$ and lognormal for $\beta = 1$.
- $\nu$ is the volatility of the volatility.
- $\rho$ is the correlation between the interest rate and its volatility.
- $W_1$ and $W_2$ are Brownian motions.

$\beta$ and $\rho$ set the slope (skew) of the smile, and $\nu$ sets its curvature. In practice, $\beta$ is fixed near 0.5, and $\alpha_0$, $\rho$, and $\nu$ are calibrated to the smile of each expiry and tenor. The model gives an approximate formula for the implied Black (or normal) volatility at each strike, and Black's model then gives the price. SABR is the market standard to build the volatility surface of swaptions.

## Constant Maturity Swaps

A CMS has one leg that pays a swap rate with a fixed tenor, for example the 10-year swap rate. On each reset date $t_i$, the contract takes the 10-year swap rate of that day. The reference swap always has the same tenor of 10 years, so the name is "constant maturity". The other leg pays a fixed rate or a floating rate, for example SOFR. The CMS leg pays $L \tau_i s_i$ at $t_{i+1}$, where $s_i$ is the swap rate at $t_i$ and $\tau_i = t_{i+1} - t_i$.

The swap rate is the fixed rate that gives a zero value to a new standard swap with the reference tenor. It is the par rate $K_{par}$ in 08-swaps.md, but here the reference swap starts on the future fixing date $T_0$. Today, the market knows only the forward swap rate:

$$s_F = \frac{P(0,T_0) - P(0,T_n)}{A_0} \qquad A_0 = \sum_{j=1}^{n} \tau_j P(0,T_j)$$

$T_1, \dots, T_n$ are the payment dates of the fixed leg of the reference swap, for example 10 annual dates.
$A_0$ is the annuity of the reference swap.
For $T_0 = 0$, $P(0,0) = 1$, and the formula gives $K_{par}$.

For a swap on EURIBOR, the numerator is the value of the floating leg, $\sum_k \tau_k P(0,T_k) F_k$. The forward rates $F_k$ come from the EURIBOR curve, and the discount factors come from the €STR curve. For an OIS swap on SOFR or €STR, one curve gives both, so the first formula applies.


For one CMS period, the fixing date is $T_0 = t_i$ and the payment date is $T_p = t_{i+1}$. To value the payment, you need the expected swap rate under the forward measure of $T_p$. The forward swap rate $s_F$ is not this expected value:

A vanilla swap pays the floating rate of a period at the end of that period. This is the natural payment of that rate, so the expected rate is the forward rate $F_k$.
The natural payment of a swap rate is an annuity, because a swap pays its fixed rate on all $n$ dates of its fixed leg. Thus $s_F$ is the expected value under the annuity measure, with $A_t$ as the numeraire.
A CMS pays the swap rate only once, on one date. This difference causes the adjustment.

The change of measure gives

$$E^{T_p}[s_{T_0}] = \frac{A_0}{P(0,T_p)} E^{A}\left[s_{T_0} \frac{P(T_0,T_p)}{A_{T_0}}\right]$$

If the swap rate increases, the annuity $A_{T_0}$ decreases, and the ratio $P(T_0,T_p)/A_{T_0}$ increases. The ratio and the swap rate move together, so the expected swap rate is higher than $s_F$.

Hull gets the same result from bond convexity. Think of the swap rate as the yield of a bond. Under the forward measure, the expected bond price is equal to the forward bond price. The price is a convex function of the yield, so the expected yield is higher than the forward yield (Jensen's inequality).

The same result follows from the payoffs at the fixing date. The payoff of a payer swap that starts on the fixing date is a concave function of the swap rate, because its annuity falls when the rate rises, so it gains less than a straight line when rates rise and loses more when rates fall. A CMS that receives the swap rate and pays a fixed rate has a linear payoff. When each contract has the fixed rate that gives it a zero value today, both have an expected payoff of zero under the forward measure of the fixing date. The swap payoff is zero at the forward swap rate, and the CMS payoff is zero at the expected swap rate, which is higher because the swap payoff is concave. The CMS payoff is higher than the swap payoff when the rate moves far from the forward in either direction, and the higher fixed rate of the CMS offsets these larger payoffs. The gap between the two rates is the convexity adjustment.

![Payoff of a vanilla payer swap and of a CMS against the swap rate at the fixing date, with the forward swap rate, the expected swap rate, and the convexity adjustment](Attachments/cms-vs-vanilla-swap-payoff.svg)

The curves come from a 30-year swap with annual payments on a flat curve. The CMS has the same slope as the swap at the forward and pays on the fixing date.



## Inflation Swaps


TODO European swaption Chapter 29