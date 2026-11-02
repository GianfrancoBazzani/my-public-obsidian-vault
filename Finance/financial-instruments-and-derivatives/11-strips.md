# STRIPS

## STRIPS

STRIPS (**Separate Trading of Registered Interest and Principal Securities**) are the separate cash flows of a coupon bond, each traded as its own security. A dealer splits the bond so that every coupon and the principal trade separately.

**Example**

A 3-year bond with a 4% annual coupon, a face value of €100 and a price of €100 splits into four securities.

| STRIP | Payment | Date |
| --- | --- | --- |
| Coupon 1 | €4 | Year 1 |
| Coupon 2 | €4 | Year 2 |
| Coupon 3 | €4 | Year 3 |
| Principal | €100 | Year 3 |

Each STRIP pays one amount on one date, so each STRIP is a zero-coupon bond. The Coupon 3 STRIP and the Principal STRIP pay on the same date but are different securities.

## Pricing STRIPS

Each STRIP is a zero-coupon bond, so its price is its single cash flow discounted from its maturity date.

$$\text{Price} = \frac{\text{Final cash flow}}{(1+r)^t}$$

**Example**

A €4 coupon that is paid in 2 years, with a discount rate of 3%, is worth €3.77.

$$\frac{4}{(1.03)^2} = €3.77$$

With the same 3% rate for all dates, the four STRIPS of the 3-year 4% bond have these prices.

| STRIP | Calculation | Price |
| --- | --- | --- |
| Coupon 1 | $4/(1.03)^1$ | €3.88 |
| Coupon 2 | $4/(1.03)^2$ | €3.77 |
| Coupon 3 | $4/(1.03)^3$ | €3.66 |
| Principal | $100/(1.03)^3$ | €91.51 |
| **Total** | | **€102.83** |

The rounded prices add up to €102.82, and the unrounded prices give €102.83. The total is above €100 because the 4% coupon is higher than the 3% discount rate.

The total of the STRIPS must equal the price of the original bond. If the STRIPS cost less than the bond, a dealer buys the STRIPS, puts them back together into the bond (**reconstitution**) and sells the bond for a profit. If the STRIPS cost more, the dealer buys the bond, splits it and sells the STRIPS.

## Use Cases

A normal bond pays a cash flow every year, and a STRIP pays a single cash flow at maturity.

| Year | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- |
| 5-year 4% bond | €4 | €4 | €4 | €4 | €104 |
| 5-year STRIP | | | | | €50,000 |

This single cash flow gives STRIPS five advantages.

- **No reinvestment risk.** A STRIP pays nothing before maturity, so there are no coupons to reinvest at unknown rates.
- **Exact maturity and duration.** The investor chooses the exact date of the cash flow, and the duration of a STRIP equals its maturity. A zero-coupon bond has the highest duration for its maturity, which gives a large and clear exposure to interest rates.
- **Flexibility.** The investor combines STRIPS of different maturities to build a portfolio with any custom schedule of cash flows.
- **Transparency.** The price is one discounted cash flow, so it is very easy to calculate.
- **Spot rates.** The price of each STRIP gives the zero-coupon rate for its date directly, which helps to build the yield curve.

**Example (cash flow matching)**

An investor needs exactly €50,000 in 5 years and buys a 5-year STRIP with a face value of €50,000. The STRIP pays the full amount on the date of the liability, with no coupons to reinvest and no bond to sell before maturity. At a 3% discount rate, the STRIP costs €43,130.44.

$$\frac{50{,}000}{(1.03)^5} = €43{,}130.44$$
