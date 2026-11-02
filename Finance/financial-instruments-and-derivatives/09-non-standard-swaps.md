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

The holder receives this payoff $mn$ times, once per period of an $n$-year swap. Discounted to the expiry and added, these cash flows equal $\max(s_T - s_K, 0)$ (payer) or $\max(s_K - s_T, 0)$ (receiver) times the annuity of the swap.

A use case of swaptions is to provide companies with a guarantee that the fixed rate of interest they will pay on a loan at some future time will not exceed some level. They are an alternative to forward swaps. Forward swaps involve no up-front cost but have the disadvantage of obligating the company to enter into a swap agreement. With a swaption, the company is able to benefit from favorable interest rate movements while acquiring protection from unfavorable interest rate movements.

After exercise, a swaption gives a cash flow on each payment date of the underlying swap. The payoffs on each payment date are

$$\text{Payer payoff} = \frac{L}{m} \max(s_T - s_K, 0)$$

$$\text{Receiver payoff} = \frac{L}{m} \max(s_K - s_T, 0)$$

where

- $L$ is the principal (notional) of the underlying swap.
- $m$ is the number of payments per year of the swap, so $L/m$ is the principal times the accrual fraction of one period.
- $s_T$ is the swap rate at the expiry $T$ of the swaption, which is the fixed rate of a new swap at that date.
- $s_K$ is the strike swap rate, which is the fixed rate that the holder pays (payer) or receives (receiver) after exercise.



## Caps and Floors

TODO Hull Chapter 34

## SABR model

## Constant Maturity Swaps

## Inflation Swaps


TODO European swaption Chapter 29