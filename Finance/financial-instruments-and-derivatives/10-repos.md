# Repos

## Repos

A repo (**REPurchase agreement**) is a collateralized loan in which the borrower gives a bond to the lender as collateral.

**Example**

A bank needs €60M for 21 days and uses a Bund (German government bond) as collateral. The repo rate is 2%.

- **Day 0:** the bank delivers a Bund worth €60M and receives €60M in cash.
- **Day 21:** the bank pays back €60M plus interest and gets its original Bund back.

The interest uses the ACT/360 day count convention.

$$\text{Interest} = 60M \times 2\% \times \frac{21}{360} = €0.07M$$

| Day | Bank gives | Bank receives |
| --- | --- | --- |
| 0 | Bund | €60M |
| 21 | €60.07M | Bund |

The total repayment is €60.07M (€60M of principal plus €70,000 of interest).

### General Collateral vs Special Repo

| | General Collateral (GC) | Special Repo |
| --- | --- | --- |
| Collateral | Any eligible bond | One specific bond |
| Repo rate | Normal market rate | Lower than the GC rate |
| Example rate | 3.2% | 2.5% |
| Ease of execution | Easy | Difficult |

A special repo is cheaper because the bond is in high demand and scarce. Cash lenders who need that specific bond (e.g. to cover a short position) accept a lower rate on their cash to get it. The holder of the bond can therefore borrow on better terms than with GC. The spread between the GC rate and the special rate (0.7% in the example) shows how "special" the bond is.

### Repo Curve

The repo curve shows the repo rate for each term, from overnight (1D) to several months.

| Term | 1D | 1W | 1M | 3M | 6M |
| --- | --- | --- | --- | --- | --- |
| Repo rate | 2.8% | 3.0% | 3.2% | 3.5% | 3.8% |

An upward-sloping curve, as in the table, is the normal situation, and longer terms pay higher rates for two reasons.

- **Term premium.** A cash lender that locks its cash for a longer term gives up liquidity and asks for a higher rate.
- **Rate expectations.** A term repo rate is close to the average of the overnight rates expected over the term. A steep curve signals expected rate hikes, and an inverted curve signals expected rate cuts.

The curve is of interest to traders for three reasons.

- **Funding cost.** A dealer that buys a bond and finances it with a repo earns the carry, which is the coupon income minus the repo cost. With a bond that yields 3.4%, overnight funding at 2.8% gives a positive carry of 0.6%, while 6M funding at 3.8% gives a negative carry of 0.4%.
- **Choice of term.** Overnight funding is the cheapest, but the dealer must roll it every day and is exposed to a rise in rates or a loss of funding. A term repo locks the rate and the cash for the whole term at a higher cost.
- **Pricing of bond forwards and futures.** The repo rate for the delivery term is the financing rate in the cost of carry of a bond (see [Futures and Forwards Pricing](05-futures-and-forwards-pricing.md)), and it enters the net basis of bond futures (see [FRAs and Interest Rate Futures](07-fras-and-interest-rate-futures.md)).

### Haircuts

A haircut is a safety margin for the cash lender. The lender lends less cash than the market value of the collateral, so it stays protected if the collateral loses value.

$$\text{Cash lent} = \text{Market value of the collateral} \times (1 - \text{Haircut})$$

**Example**

A bond is worth €100M in the market. With a haircut of 2%, the lender lends only €98M. In the Bund example above, a 2% haircut means that the bank must deliver a Bund worth €60M / 0.98 ≈ €61.22M to receive €60M.

| Collateral | Typical haircut |
| --- | --- |
| German Bund 10Y | 1–2% |
| Spanish government bond 10Y | 3–4% |
| AAA corporate bond | 5–8% |
| High yield bond | 15–25% |

The haircut increases when the credit quality or the liquidity of the collateral decreases, because the lender may need to sell it after a default at a lower price.
