# Interest Rates

An **interest rate** defines the amount of money that a borrower promises to pay the lender for the use of the funds, for example a mortgage rate or a deposit rate. The rate depends on the currency, the tenor, the compounding frequency (see [02-interest-rates-curves](02-interest-rates-curves.md)) and the credit risk of the borrower.

Rate changes and spreads are quoted in **basis points** (bp). One basis point is 0.01% per annum, or 0.0001.

## Credit Risk

**Credit risk** is the risk that the borrower defaults and does not pay the interest or the principal as promised. A higher credit risk requires a higher promised rate.

### Risk Free Rate

The government of a developed country is assumed not to default on debt in its own currency, because its central bank can create the money to pay. Its Treasury bills and bonds are therefore the usual risk-free benchmark. The assumption has three limits.

- **Monetary sovereignty is required.** Greece restructured its euro debt in 2012, the largest sovereign restructuring in history, because a euro member cannot print euros.
- **Only default risk is removed.** A Treasury bond still carries inflation risk and price changes before maturity.
- **Treasury rates are slightly too low.** Regulation and capital rules make banks hold Treasuries, and US Treasuries have a favorable tax treatment. The extra demand lowers their yield, so derivatives traders use OIS rates as the risk-free proxy instead.

### Credit Spread

The **credit spread** is the extra rate over the risk-free rate that compensates for credit risk. It has three parts.

- **Expected loss.** $EL = PD \times LGD$, the probability of default times the loss given default. A 2% default probability with a 40% loss gives 80 bp per year.
- **Credit risk premium.** Compensation for the uncertainty of the loss, because defaults cluster in recessions, when other assets also lose value.
- **Liquidity premium.** Compensation for a bond that is harder to sell than a government bond.

### Reference Rates

A **reference rate** is a benchmark rate that an independent administrator or a central bank publishes every business day. A floating-rate contract pays the reference rate plus a spread, observed again on each reset date.

- **Floating-rate loans and bonds.** Mortgages, corporate loans and floating-rate notes pay the reference rate plus a spread for the credit risk of the borrower.
- **Interest rate derivatives.** Swaps, FRAs, futures, caps and floors compute their floating payments from it.
- **Discounting.** Collateralized derivatives are discounted with overnight indexed swap (OIS) rates, because cash collateral earns the overnight rate.
- **Credit spreads.** Risky bond yields are quoted as a spread over a Treasury or swap rate.
- **Monetary policy.** Central banks steer the overnight rate (the Fed with a target range for the federal funds rate, the ECB with its deposit facility rate), and the change passes to all other rates.

To resist manipulation, a reference rate should be anchored in real transactions. LIBOR came from bank estimates, so the market replaced it with transaction-based overnight rates. EURIBOR was reformed instead, and since 2019 a hybrid methodology uses panel-bank transactions when available and models otherwise. It remains the main rate for floating-rate loans and mortgages in the euro area, next to €STR.

## Types of Rates

TODO

### LIBOR and EURIBOR

TODO

### Treasury Rates

TODO

### Overnight Rates

TODO

### Repo Rates

TODO

## Liquidity preference theory

TODO Explain upward rates