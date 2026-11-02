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



## Caps and Floors

TODO Hull Chapter 34

## SABR model

## Constant Maturity Swaps

## Inflation Swaps


TODO European swaption Chapter 29