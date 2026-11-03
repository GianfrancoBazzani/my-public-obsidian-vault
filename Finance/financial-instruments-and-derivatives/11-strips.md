# STRIPS

## STRIPS

STRIPS (**Separate Trading of Registered Interest and Principal of Securities**) are the separate cash flows of a coupon bond, each traded as its own security. The holder of the bond can ask a bank, a broker or a dealer for the split at any time until maturity. Investors buy and hold STRIPS only through these institutions, not from the Treasury. Each STRIP stays a direct obligation of the U.S. government, with the credit risk of the original bond.

The name comes from the U.S. Treasury program, which started in 1985 and now covers the notes, the bonds and the TIPS. Bills (already zero-coupon) and floating-rate notes cannot be split. In June 2025, USD 560 billion of Treasuries were held as STRIPS, 2.5% of the USD 22.2 trillion of notes, bonds and TIPS. Before 1985, dealers sold their own zero-coupon receipts on Treasury bonds, such as TIGRs and CATS. Other governments also allow the split, for example France since 1991 (the first in Europe) and Germany and the United Kingdom since 1997.

**Example**

A 3-year bond with a 4% annual coupon and a face value of €100 splits into four securities.

| STRIP | Payment | Date |
| --- | --- | --- |
| Coupon 1 | €4 | Year 1 |
| Coupon 2 | €4 | Year 2 |
| Coupon 3 | €4 | Year 3 |
| Principal | €100 | Year 3 |

Each STRIP pays one amount on one date, so each STRIP is a zero-coupon bond. U.S. Treasury notes and bonds pay a coupon every six months, so a note with 10 years to maturity splits into 21 STRIPS (20 coupons and the principal).

In the U.S., the coupon STRIPS that pay on the same date share one identification code (CUSIP) and are interchangeable, even if they come from different notes and bonds. Each principal STRIP has its own code and belongs to one bond only, so the Coupon 3 STRIP and the Principal STRIP pay on the same date but are different securities.

## Pricing STRIPS

The price of a STRIP is its single cash flow discounted from its maturity date at the zero rate $r$ of that date.

$$\text{Price} = \frac{\text{Final cash flow}}{(1+r)^t}$$

U.S. STRIPS are quoted in percent of the face value, and their rates use semiannual compounding, as the coupons of Treasuries do, so the denominator is $(1 + r/2)^{2t}$.

**Example**

With the same 3% rate for all dates, the four STRIPS of the 3-year 4% bond have these prices.

| STRIP | Calculation | Price |
| --- | --- | --- |
| Coupon 1 | $4/(1.03)^1$ | €3.88 |
| Coupon 2 | $4/(1.03)^2$ | €3.77 |
| Coupon 3 | $4/(1.03)^3$ | €3.66 |
| Principal | $100/(1.03)^3$ | €91.51 |
| **Total** | | **€102.83** |

The unrounded prices add up to €102.83 (the rounded prices to €102.82), which is the price of the bond at a 3% yield. It is above the face value of €100 because the 4% coupon is higher than the 3% discount rate.

The total of the STRIPS must equal the full (dirty) price of the bond (see [Fixed Income Securities](00-fixed-income-securities.md#clean-and-dirty-prices)), up to the transaction costs. If the STRIPS cost less than the bond, a dealer buys the STRIPS, puts them back together into the bond (**reconstitution**) and sells the bond for a profit. Reconstitution needs the principal STRIP of the bond and one coupon STRIP for each remaining payment date. If the STRIPS cost more, the dealer buys the bond, splits it and sells the STRIPS, for example with a profit of €0.33 per €100 of face value if the bond trades at €102.50. These trades keep the price of the bond very close to the total of its STRIPS.

## Use Cases

A normal bond pays a cash flow every year, and a STRIP pays a single cash flow at maturity, as the table shows for a face value of €50,000.

| Year | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- |
| 5-year 4% bond | €2,000 | €2,000 | €2,000 | €2,000 | €52,000 |
| 5-year STRIP | | | | | €50,000 |

This single cash flow gives STRIPS five advantages.

- **No reinvestment risk.** A STRIP pays nothing before maturity, so there are no coupons to reinvest at unknown rates, and an investor who holds it to maturity earns exactly the yield at purchase.
- **Exact maturity and duration.** The investor chooses the exact date of the cash flow, and the Macaulay duration of a STRIP equals its maturity (see [Fixed Income Securities](00-fixed-income-securities.md#macaulay-duration)). A zero-coupon bond has the highest duration for its maturity, which gives a large exposure to the zero rate of a single date only.
- **Flexibility.** The investor combines STRIPS of different maturities to build any schedule of cash flows on the available payment dates.
- **Transparency.** The price is one discounted cash flow, so it is easy to calculate.
- **Spot rates.** The price of each STRIP gives the zero rate of its date directly, for example $(100/91.51)^{1/3} - 1 \approx 3\%$ for the Principal STRIP above, which helps to build the zero curve without a bootstrap (see [Interest Rate Curves](02-interest-rates-curves.md#bootstrapping)). Principal STRIPS often trade at higher prices than coupon STRIPS of the same date, so the two types give slightly different rates.

**Example (cash flow matching)**

An investor needs exactly €50,000 in 5 years and buys a 5-year STRIP with a face value of €50,000. The STRIP pays the full amount on the date of the liability, with no coupons to reinvest and no bond to sell before maturity. At a 3% discount rate, the STRIP costs €43,130.44.

$$\frac{50{,}000}{(1.03)^5} = €43{,}130.44$$

Pension funds and insurance companies buy STRIPS in this way to match their liabilities, and speculators buy long STRIPS for their high duration.

## Disadvantages

The single cash flow also gives STRIPS two disadvantages.

- **Price risk.** The high duration makes the price of a long STRIP very sensitive to interest rates. If the rate rises from 3% to 4%, the price of a 30-year STRIP (Macaulay duration of 30 years) falls by 25%, from €41.20 to €30.83, and the price of a 30-year 4% bond (19.1 years) by only 16%, from €119.60 to €100.00. An investor who holds the STRIP to maturity still receives the full face value.
- **No cash before maturity.** A STRIP pays no income before maturity, but in the U.S. the holder still pays federal income tax each year on the interest that accrues.
