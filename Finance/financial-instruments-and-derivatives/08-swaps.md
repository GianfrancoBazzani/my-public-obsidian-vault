# Swaps

A swap is an OTC agreement between two companies to exchange future cash flows. It defines the payment dates and how each cash flow is calculated, usually from the future value of an interest rate, an exchange rate, or another market variable. A forward contract can be viewed as a simple swap.

## Interest Rate Swaps (IRS)

An interest rate swap is a swap where interest at a predetermined fixed rate, applied to a certain principal, is exchanged for interest at a floating reference rate, applied to the same principal, with regular exchanges begin made for an agreed period of time. An IRS has two legs, and each leg is one side’s stream of payments.

For example, a swap negotiated in the past might exchange 3% interest on a $100 million principal for three-month LIBOR on the same principal, every three months for five years.

As LIBOR is phased out, swaps on overnight rates, called **overnight indexed swaps (OIS)**, are becoming more popular. An OIS longer than one year is typically divided into three-month subperiods. At the end of each subperiod, the fixed rate, called the **OIS rate**, is exchanged for a three-month reference rate compounded from that subperiod's one-day rates. OISs of ten years or longer now trade. Unlike forward-looking LIBOR, which was fixed at the start of each period, this compounded rate is backward-looking and known only at the end of the period (see [FRAs and Interest Rate Futures](07-fras-and-interest-rate-futures.md)).

The principal of an IRS is never exchanged, which is why it is called notional. An exchange would change nothing, because at the start and at maturity each side would pay and receive the same amount in the same currency, so the net cash flows stay the same.

Each side is named after the fixed leg. The **payer** pays fixed and receives floating, gains when rates rise, and lets a floating-rate borrower fix its cost. The **receiver** receives fixed and pays floating, gains when rates fall, and lets a fixed-rate borrower float its debt.

### Valuation

An IRS is equivalent to a portfolio of FRAs, one for each payment date, where each FRA exchanges the fixed rate $R_K$ for the floating rate of its period (see [FRAs and Interest Rate Futures](07-fras-and-interest-rate-futures.md)). Each FRA is valued by assuming that its forward rate $R_{F,i}$ is realized and by discounting the resulting cash flow, so the swap value is the sum of the FRA values.

$$V_{\text{payer}} = \sum_{i=1}^{n} L \tau_i (R_{F,i} - R_K) DF(t_i)$$

Splitting this sum into its floating and fixed terms gives the two legs. To find the present value of a swap, we therefore discount the future cash flows of each leg separately and then aggregate them.

#### Fixed Leg

The **annuity** $A$ is the present value of receiving a rate of one unit at each payment date, per unit of notional. Here $\tau_i$ is the year fraction of period $i$ and $DF(t_i)$ is the discount factor for date $t_i$.

$$A = \sum_{i=1}^{n} \tau_i DF(t_i)$$

$$PV_{\text{fixed}} = L R_K A$$

The fixed leg is only a series of coupons, so the annuity gives the present value of all of them. $R_K$ is the fixed rate, which is the same for all periods, and $L$ is the notional.

#### Floating Leg

We can value the floating leg with the forward rates $R_{F,i}$ that today's curve implies.

$$PV_{\text{float}} = \sum_{i=1}^{n} L \tau_i R_{F,i} DF(t_i)$$

The forward rate of period $i$ is defined so that an investment until $t_{i-1}$, reinvested at $R_{F,i}$ until $t_i$, gives the same result as an investment until $t_i$ (see [Interest Rate Curves](02-interest-rates-curves.md)).

$$1 + \tau_i R_{F,i} = \frac{DF(t_{i-1})}{DF(t_i)} \implies \tau_i R_{F,i} DF(t_i) = DF(t_{i-1}) - DF(t_i)$$

If we substitute this equality into $PV_{\text{float}}$, the sum telescopes.

$$PV_{\text{float}} = L \sum_{i=1}^{n} \left[ DF(t_{i-1}) - DF(t_i) \right]$$

Each term cancels part of the next one, and only the first and the last terms remain. Because $t_0$ is today, $DF(t_0) = 1$.

$$PV_{\text{float}} = L \left[ DF(t_0) - DF(t_n) \right] = L \left[ 1 - DF(t_n) \right]$$

To receive the floating rate on $L$ until $t_n$ thus has the same present value as to receive $L$ today and repay it at $t_n$. No forward rate appears in the result, because all of them cancel. This result holds when the same curve gives the forward rates and the discount factors, and when the first period starts today.

> [!NOTE]
> **Where the telescoping sum applies**
>
> The sum telescopes for any swap whose forward rates and discount factors come from the same curve. The type of floating rate alone does not decide it.
>
> - **OIS (€STR, SOFR).** The sum is exact when the swap is discounted on the curve of its own overnight rate, which is the market standard for collateralized swaps.
> - **LIBOR swaps before 2008.** The sum was exact, because one LIBOR curve gave both the forward rates and the discount factors.
> - **EURIBOR swaps today.** The sum does not telescope. The forward rates come from the EURIBOR curve and the discount factors from the €STR curve, so $1 + \tau_i R_{F,i} \neq DF(t_{i-1}) / DF(t_i)$ and each term of $PV_{\text{float}}$ must be calculated separately.
> - **Other breaks.** A spread $s$ on the floating leg does not telescope and adds $L s A$. A payment lag, or a payment date different from the end of the accrual period, also makes the result approximate.

#### Swap Value

The payer receives the floating leg and pays the fixed leg, so the value of the swap is the difference of the two legs.

$$V_{\text{payer}} = PV_{\text{float}} - PV_{\text{fixed}} = L \left[ 1 - DF(t_n) \right] - L R_K A$$

If we take $L A$ out as a common factor, the first term becomes the par swap rate $R_{\text{par}} = \left[ 1 - DF(t_n) \right] / A$ (see Par Swap Rate below).

$$V_{\text{payer}} = L A \left[ \frac{1 - DF(t_n)}{A} - R_K \right] = L A (R_{\text{par}} - R_K) \qquad V_{\text{receiver}} = L A (R_K - R_{\text{par}})$$

The swap is thus a **rate difference** $R_{\text{par}} - R_K$ on $L$, received at each payment date and discounted.

### Par Swap Rate

The **par swap rate** $R_{\text{par}}$ is the value of $R_K$ that makes the swap worth zero. It is the **swap rate** that the market quotes for each maturity. A new swap is usually set at this rate, so it is worth zero at the start.

$$R_{\text{par}} = \frac{1 - DF(t_n)}{A} = \frac{1 - DF(t_n)}{\sum_{i=1}^{n} \tau_i DF(t_i)}$$

This is the same formula as the par yield of a bond (see [Interest Rate Curves](02-interest-rates-curves.md)). The par swap rate is thus the coupon of a fixed-rate bond that is worth its principal. After the start, $R_{\text{par}}$ changes with the curve while $R_K$ stays fixed. The payer gains when $R_{\text{par}}$ rises above $R_K$, and the receiver gains when it falls below $R_K$.

### Zero Curve

The discount factors $DF(t_i)$ in the formulas above come from the zero curve (see [Interest Rate Curves](02-interest-rates-curves.md)). The market does not quote zero rates directly. It quotes instruments such as OIS rates and swap rates, and the zero curve is **bootstrapped** from these quotes.

An OIS at the quoted rate is worth zero. When it is discounted with the curve of its own overnight rate, its floating leg plus the principal at $t_n$ is worth par, so its fixed leg plus the principal is also a bond worth par. Each quote thus gives the equation $R_{\text{par}} A = 1 - DF(t_n)$. For a swap on a term rate such as EURIBOR, this is true only if the same curve gives the forward rates and the discount factors. If the discount factors until $t_n$ are known, the quoted swap rate $R_{\text{par}}(t_{n+1})$ for the next maturity has only one unknown, $DF(t_{n+1})$. We write its par condition with the annuity divided into the known terms and the last term.

$$R_{\text{par}}(t_{n+1}) \left[ \sum_{i=1}^{n} \tau_i DF(t_i) + \tau_{n+1} DF(t_{n+1}) \right] = 1 - DF(t_{n+1})$$

$DF(t_{n+1})$ is in the last coupon and in the principal, so we move both terms to the left side.

$$DF(t_{n+1}) \left[ 1 + R_{\text{par}}(t_{n+1}) \tau_{n+1} \right] = 1 - R_{\text{par}}(t_{n+1}) \sum_{i=1}^{n} \tau_i DF(t_i)$$

The factor $1 + R_{\text{par}}(t_{n+1}) \tau_{n+1}$ is the last cash flow of the par bond. If we divide by it, we get the bootstrap formula. The formula needs all the earlier discount factors and not only $DF(t_n)$, because a par rate is an average of the forward rates and does not compound period by period like them.

$$DF(t_{n+1}) = \frac{1 - R_{\text{par}}(t_{n+1}) \sum_{i=1}^{n} \tau_i DF(t_i)}{1 + R_{\text{par}}(t_{n+1}) \tau_{n+1}}$$

The bootstrap goes from the shortest maturity to the longest.

1. An OIS of one year or less usually has only one payment at maturity, so $DF(t) = 1 / (1 + R \tau)$ directly.
2. Each longer quote gives one new $DF$ from the ones already known.
3. Quotes do not cover every payment date (e.g. only 2-year and 5-year swaps with quarterly payments). Between quoted maturities, assume a shape such as linear zero rates and solve iteratively for the zero rate that prices each bond at par.
4. Each $DF$ gives the zero rate $r(t) = -\ln DF(t) / t$ (continuous compounding).

### IRS as Two Bonds

If we add and subtract the notional at $t_n$ to each leg, the two extra terms cancel, and each leg becomes a bond.

$$V_{\text{payer}} = \underbrace{\left[ PV_{\text{float}} + L DF(t_n) \right]}_{\text{floating-rate bond} = L} - \underbrace{\left[ PV_{\text{fixed}} + L DF(t_n) \right]}_{\text{bond with coupon } R_K}$$

The payer is thus long a floating-rate bond and short a fixed-rate bond with coupon $R_K$, both with the principal $L$ and the maturity $t_n$. The receiver has the opposite position.

#### Floating-Rate Bond

On a reset date, the telescoping sum above gives $L \left[ 1 - DF(t_n) \right] + L DF(t_n) = L$. The floating-rate bond is thus worth its principal at all levels of rates, because its next coupon rises and falls with the market rate.

This result is exact only on a reset date. If today is between the reset dates $t_{i-1}$ and $t_i$, the rate $R_i$ of period $i$ was already fixed on $t_{i-1}$. On $t_i$, the bond pays the coupon $L \tau_i R_i$, and the remaining bond is worth $L$ because $t_i$ is a reset date. Today the bond is worth that total discounted from $t_i$.

$$PV_{\text{float}} + L DF(t_n) = L (1 + \tau_i R_i) DF(t_i)$$

The bond thus behaves like a zero-coupon bond that matures on the next reset date $t_i$. Its duration is the time to $t_i$, which is a few months and not years. Its DV01 is small but not zero, and it goes back to zero on each reset date.

The direct consequence is that $DV01_{\text{float}} \approx 0$. All the rate sensitivity of the swap comes from the fixed-rate bond, and the payer has it with the opposite sign because the payer is short that bond. The payer thus has a **short duration position**, close to the short sale of a fixed-rate bond with the same maturity.

#### Value Through Time

1. **At the start.** $R_K$ is set at the par swap rate, so the fixed-rate bond is a par bond worth $L$, and the swap is worth zero.
2. **After the start.** The floating-rate bond returns to $L$ on each reset date, but the price of the fixed-rate bond moves with rates. If rates rise, the fixed-rate bond falls below $L$, and the payer gains because the payer is short that bond. If rates fall, the fixed-rate bond rises above $L$, and the payer loses.
3. **Toward maturity.** Each payment date removes one period from the annuity $A$, so fewer periods remain to multiply the rate difference $R_{\text{par}} - R_K$. The same move of rates thus has less effect on a shorter swap, and each net payment converts part of the value into cash.
4. **At maturity.** The two bonds repay $L$, and the value of the swap is zero again.

### Greeks

The Greeks measure how the value of a swap changes when one market factor (such as the level or the volatility of rates) changes and the others stay constant. They are the base of risk management, because a desk adds them over all its positions to know its net exposure, size its hedges, and set risk limits. For an IRS, the two main Greeks are the DV01 and the convexity.

#### DV01

$$DV01 = \Delta V \text{ for a move of } +1 \text{ bp in the curve}$$

The DV01 is the **change in value** of the position in currency, with its sign, as for a bond (see [Fixed Income Securities](00-fixed-income-securities.md#dv01)). A **payer swap** gains when rates rise, so its DV01 is **positive**. A receiver swap has a negative DV01, like a long fixed-rate bond.

From $V_{\text{payer}} = L A (R_{\text{par}} - R_K)$, a move of $R_{\text{par}}$ changes the value through the rate difference and the annuity.

$$\frac{dV_{\text{payer}}}{dR_{\text{par}}} = L A + L (R_{\text{par}} - R_K) \frac{dA}{dR_{\text{par}}}$$

For a swap at par, $R_{\text{par}} = R_K$, so the second term is zero, and $DV01 \approx L A \times 0.0001$. A 30-year swap with annual payments, a notional of EUR 100 million, and a flat curve at 4.30% has $A = 16.68$, so its DV01 is about EUR 166,800 per basis point. To hedge a fixed-rate bond portfolio, an investor enters a payer swap whose DV01 has the same size as the DV01 of the portfolio and the opposite sign.

#### Convexity

The DV01 is a linear approximation, so it is accurate only for small moves of rates. The **convexity** is the curvature of the value that the DV01 line does not capture. With the second-order term, the change in value for a move of $\Delta y$ basis points is

$$\Delta V \approx DV01 \times \Delta y + \frac{1}{2} \Gamma (\Delta y)^2$$

where $\Gamma$ is the change of the DV01 for a move of 1 bp.

The positive convexity is good for the **receiver**, and the payer has a negative convexity. A fixed-rate bond has a positive convexity, so its price falls by less when rates rise than it rises when rates fall by the same amount (see [Fixed Income Securities](00-fixed-income-securities.md#convexity)). The convexity of the floating-rate bond is almost zero, for the same reason as its DV01. The receiver is long the fixed-rate bond and thus has its positive convexity, and the payer is short the bond and has a negative convexity.

The swap formula shows the same result. The payer receives $L A (R_{\text{par}} - R_K)$, and the annuity $A$ falls when rates rise. The gains of the payer are thus multiplied by a smaller annuity, and its losses by a larger one.

For the payer, the difference from the DV01 line is **negative in the two directions**. The payer **loses more** than the line when rates fall and **gains less** when they rise. If rates can move up or down by the same amount, the average result is about $\frac{1}{2} \Gamma (\Delta y)^2$, which is negative for the payer and increases with the size of the moves. A rise in volatility thus hurts the payer and helps the receiver. The convexity increases quickly with maturity, so it is large for long swaps and small for short ones.

![P&L of a 30-year payer swap and receiver swap against the swap rate, with the DV01 linear approximation](Attachments/swap-payer-vs-receiver-convexity.svg)

The chart uses a 30-year swap with annual payments, a notional of EUR 100 million, a fixed rate of 4.30%, and a flat curve. The swap starts at par, so its value at 4.30% is zero.

| Rate move | DV01 line | Value of the payer | Effect of the convexity |
|---|---|---|---|
| +200 bp (6.30%) | +EUR 33.4 million | +EUR 26.7 million | −EUR 6.7 million |
| −200 bp (2.30%) | −EUR 33.4 million | −EUR 43.0 million | −EUR 9.6 million |

The annuity falls to 13.33 at 6.30% and rises to 21.50 at 2.30%, which explains the difference. The average of the two scenarios is −EUR 8.2 million for the payer, although the average move of rates is zero. The receiver has the same values with the opposite sign, so the curvature is good for it in the two directions.
