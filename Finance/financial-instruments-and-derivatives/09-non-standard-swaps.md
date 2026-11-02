# Non-standard Swaps

## European Swaptions

Swap options, or swaptions, are options on interest rate swaps and are another popular type of interest rate option. They give the holder the right to enter into a certain interest rate swap at a certain time in the future. The swaptions below are European, so the holder can exercise them only on one date, the expiry date.

A swaption can be regarded as an option to exchange a fixed-rate bond for the principal amount of the swap, that is, a type of bond option. If a swaption gives the holder the right to pay fixed and receive floating, it is a put option on the fixed-rate bond with strike price equal to the principal. If a swaption gives the holder the right to pay floating and receive fixed, it is a call option on the fixed-rate bond with a strike price equal to the principal.

The market calls the first a payer swaption and the second a receiver swaption.

| Swaption | Right of the holder | Bond option | Gains when rates |
|---|---|---|---|
| Payer | Pay fixed, receive floating | Put on the fixed-rate bond | Rise |
| Receiver | Receive fixed, pay floating | Call on the fixed-rate bond | Fall |

The market quotes a swaption as the option tenor followed by the tenor of the underlying swap. For example, a 2Y5Y payer is a 2-year option to enter a 5-year payer swap.

A use case of swaptions is to provide companies with a guarantee that the fixed rate of interest they will pay on a loan at some future time will not exceed some level. They are an alternative to forward swaps. Forward swaps involve no up-front cost but have the disadvantage of obligating the company to enter into a swap agreement. With a swaption, the company is able to benefit from favorable interest rate movements while acquiring protection from unfavorable interest rate movements.

After exercise, a swaption gives a cash flow on each payment date of the underlying swap. The payoffs on each payment date are

$$\text{Payer payoff} = \frac{L}{m} \max(s_T - s_K, 0)$$

$$\text{Receiver payoff} = \frac{L}{m} \max(s_K - s_T, 0)$$

where

- $L$ is the principal (notional) of the underlying swap.
- $m$ is the number of payments per year of the swap, so $L/m$ is the principal times the accrual fraction of one period.
- $s_T$ is the swap rate at the expiry $T$ of the swaption, which is the fixed rate of a new swap at that date.
- $s_K$ is the strike swap rate, which is the fixed rate that the holder pays (payer) or receives (receiver) after exercise.

The holder receives this payoff $mn$ times, once per period of an $n$-year swap. Discounted to the expiry and added, these cash flows equal $\max(s_T - s_K, 0)$ (payer) or $\max(s_K - s_T, 0)$ (receiver) times the annuity of the swap.

The payment dates of the swap are $T_1, T_2, \dots, T_{mn}$, in years from today, with $T_i \approx T + i/m$. For a payer swaption, each cash flow is the payoff of a call option on $s_T$ with strike price $s_K$. A cap is a portfolio of options on interest rates, but a swaption is a single option on the swap rate with repeated payoffs.

The standard market model (Black's model) gives the value of a payer swaption as

$$V_{\text{payer}} = \sum_{i=1}^{mn} \frac{L}{m} P(0, T_i) [s_F N(d_1) - s_K N(d_2)]$$

and the value of a receiver swaption as

$$V_{\text{receiver}} = \sum_{i=1}^{mn} \frac{L}{m} P(0, T_i) [s_K N(-d_2) - s_F N(-d_1)]$$

with

$$d_1 = \frac{\ln(s_F/s_K) + \sigma^2 T/2}{\sigma \sqrt{T}}$$

$$d_2 = \frac{\ln(s_F/s_K) - \sigma^2 T/2}{\sigma \sqrt{T}} = d_1 - \sigma \sqrt{T}$$

where

- $s_F$ is the forward swap rate at time zero, which is the fixed rate that gives a zero value today to the swap that starts at $T$.
- $\sigma$ is the volatility of the forward swap rate, so $\sigma \sqrt{T}$ is the standard deviation of $\ln s_T$.
- $P(0, T_i)$ is the discount factor from today to the payment date $T_i$.
- $N(\cdot)$ is the cumulative distribution function of the standard normal distribution.

The sum $\sum_{i=1}^{mn} \frac{L}{m} P(0, T_i)$ is the annuity of the forward swap today, so the value of a payer swaption is the annuity times $[s_F N(d_1) - s_K N(d_2)]$.



## Caps and Floors

TODO Hull Chapter 34

## SABR model

## Constant Maturity Swaps

## Inflation Swaps


TODO European swaption Chapter 29