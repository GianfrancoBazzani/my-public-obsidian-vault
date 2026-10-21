## Asset Swaps TODO Move to another more advanced note

An asset swap is a strategy that combines the purchase of a fixed-coupon security with the entry into an Interest Rate Swap (IRS). The investor pays the fixed coupons to the swap counterparty and receives floating payments in exchange. The swap transforms the fixed cash flows of the security into floating cash flows. 

When we buy a fixed-income security, it usually has a fixed coupon (e.g. 5% every year). Sometimes, instead of a fixed coupon rate, we want exposure to the floating interest rate paid at that moment.

Asset swaps are widely used in fixed income trading strategies to hedge interest rate risk. The swap removes most of the sensitivity of the position to changes in interest rates, but the investor keeps the credit risk of the issuer. For this reason, the asset swap spread is a common measure of the credit risk of a fixed-income security.

### Mechanics of the Asset Swap

1. **Purchase of the security:** the investor pays the market price of the security.
2. **Entry into the IRS:**
   - Pays: the fixed rate of the swap.
   - Receives: the floating rate (EURIBOR/SOFR + spread).
3. **Net cash flows:** pure floating exposure.

### Asset Swap Spread

$$\text{ASW Spread} = (\text{Coupon} - \text{Swap Rate}) \times \frac{100}{\text{Price}}$$

**Interpretation:** the ASW spread is the additional spread over the floating reference rate that the investor receives for the credit risk.


**Example**

Corporate bond XYZ:

- Coupon: 6.5% per year.
- Price: 104.
- Maturity: 5 years.

Market:

- 5-year swap rate: 4.2%.
- 5-year government bond yield: 3.8%.

ASW spread calculation, with the rates in percent:

$\text{ASW} = (6.5 - 4.2) \times (100/104) = 2.3 \times 0.962 = 2.21$%

Comparison:

- Credit spread over the government bond: 6.5% - 3.8% = 2.7%.
- ASW spread: 2.21%.
- Difference: 49 bp, because the bond price is above par.

### Asset Swap Applications

**Why this is interesting**

A fixed-rate security packages two risks: interest rate risk and credit risk. The asset swap separates them. The investor keeps the credit risk of the issuer and passes the interest rate risk to the swap counterparty. The position behaves like a floating-rate note issued by XYZ.

- **Pure credit view.** If the investor thinks the credit of XYZ is cheap, the asset swap pays only for that view. A rate move does not change the result.
- **Comparable numbers.** The ASW spread puts every fixed-income security on one scale: spread over the swap curve. A 3-year bond at 98 and a 7-year bond at 105 become directly comparable.
- **Access to fixed-rate supply.** Most corporate bonds are fixed-rate, but many investors need floating cash flows. The asset swap converts the available supply into the required form.
- **Floating-rate funding.** A bank funds itself at a floating rate. It buys the security, swaps it, and locks the margin between "floating + ASW spread" and its floating funding cost.

**When this is not interesting**

- **The investor wants duration.** If the investor expects rates to fall, the swap removes the price gain that the investor wants.
- **Costs are high relative to the spread.** The swap bid-offer, the collateral requirements, and the counterparty risk can consume a small ASW spread.
- **The security has embedded options.** A callable or puttable bond does not have certain fixed cash flows. A standard asset swap does not hedge it well.
- **Rates are stable.** The value of the duration hedge is low when rate uncertainty is low. The swap then adds cost with little benefit.

**Practical applications**

- **Relative value analysis.** Compare the ASW spreads of different issuers with the same maturity. A wider spread means more compensation per unit of credit risk.
- **Bond vs. CDS arbitrage.** If the ASW spread is greater than the CDS spread of the same issuer, buy the security, swap it, and buy protection. The position earns the difference with little net credit risk. This is the CDS-bond basis trade.
- **Sector rotation.** Compare the average ASW spread of each sector against its history. Identify sectors that are cheap or expensive relative to their usual level.
- **Portfolio construction.** Use asset-swapped securities as the base of a credit-neutral portfolio. The portfolio then has credit exposure only, with no duration exposure.
