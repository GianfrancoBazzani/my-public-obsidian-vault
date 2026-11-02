# Non-standard Swaps

## Swaptions

Swap options, or swaptions, are options on interest rate swaps and are another popular type of interest rate option. They give the holder the right to enter into a certain interest rate swap at a certain time in the future.

A swaption can be regarded as an option to exchange a fixed-rate bond for the principal amount of the swap, that is, a type of bond option. If a swaption gives the holder the right to pay fixed and receive floating, it is a put option on the fixed-rate bond with strike price equal to the principal. If a swaption gives the holder the right to pay floating and receive fixed, it is a call option on the fixed-rate bond with a strike price equal to the principal.

The market calls the first a payer swaption and the second a receiver swaption.

| Swaption | Right of the holder | Bond option | Gains when rates |
|---|---|---|---|
| Payer | Pay fixed, receive floating | Put on the fixed-rate bond | Rise |
| Receiver | Receive fixed, pay floating | Call on the fixed-rate bond | Fall |

The market quotes a swaption as the option tenor followed by the tenor of the underlying swap. For example, a 2Y5Y payer is a 2-year option to enter a 5-year payer swap.

At exercise, the payoffs of the two swaptions are

$$\text{Payer payoff} = \max(S - K, 0) \times \text{Annuity}$$

$$\text{Receiver payoff} = \max(K - S, 0) \times \text{Annuity}$$

where $S$ is the swap rate at expiry, $K$ is the strike (the fixed rate of the swaption), and the annuity is the notional times the sum of the accrual fractions times the discount factors of the underlying swap.

An use case of swaptions is provide companies with a gurarantee that the fixed rate fo interest they will pay on aloan at some future time will not eexceed some level. They are an alterative to forward swaps. Forward swaps involve no up-front cost but have the disadvantage of obligating the company to en ter into a swap agreement. With a swaption, the company is able to benefit from favorable interest rate movements while acquiring protection from unfavorable interest rate movements.




## Caps and Floors

TODO Hull Chapter 34

## SABR model

## Constant Maturity Swaps

## Inflation Swaps


TODO European swaption Chapter 29