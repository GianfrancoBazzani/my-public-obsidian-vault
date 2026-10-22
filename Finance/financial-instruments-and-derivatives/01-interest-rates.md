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


## Types of Rates

For any given currency, many different types of interest rates are regularly quoted.

### LIBOR

**LIBOR** (London Interbank Offered Rate) was the rate at which a panel of large banks estimated they could borrow unsecured funds from other banks. Each day before 11:00 London time, the banks submitted estimates for 5 currencies (USD, GBP, EUR, CHF, JPY) and 7 tenors from overnight to 12 months, down from 10 currencies and 15 tenors before 2013. The top and bottom quartiles of the submissions were discarded and the rest averaged. LIBOR ended between 2021 and 2024 (the last synthetic USD settings stopped in September 2024) for two reasons. It relied on judgment rather than trades, so it could be manipulated, as the 2012 rate-rigging scandal showed. After 2008, the unsecured interbank term market that it measured also became too thin.

### EURIBOR

**EURIBOR** (Euro Interbank Offered Rate) is the rate at which banks in the EU and EFTA (European Free Trade Association) countries can borrow unsecured wholesale funds in euro. It started with the euro on 1 January 1999 and replaced national rates. The European Money Markets Institute (EMMI) publishes it every business day at 11:00 CET for 5 tenors (1 week, 1, 3, 6 and 12 months), from a panel of about 20 banks. Like LIBOR it was quote-based and was manipulated, and the European Commission fined several banks in 2013 and 2016 for a EURIBOR cartel of 2005–2008. It was reformed instead of discontinued, and since 2019 a hybrid methodology uses the real transactions of the panel banks when available and otherwise data interpolated or market-adjusted from earlier transactions. It is a critical benchmark under the EU Benchmarks Regulation, supervised by ESMA since 2022, and it indexes the floating leg of most euro swaps (3 or 6 months) and floating-rate mortgages (12 months in Spain, 6 months in Portugal).

### Treasury Rates

**Treasury rates** are the yields on the bills, notes and bonds that a government issues to borrow in its own currency, and they are the usual risk-free rates, with the limits given above. Auctions and secondary trading set them, and the US Treasury publishes them every business day as a par yield curve from 1 month to 30 years. The euro area has no single Treasury, so the German Bund is the benchmark and other sovereigns are quoted as a spread over it, for example the BTP–Bund spread. Treasury rates are also the base of the G-spread of corporate bonds.

### Overnight Rates

**€STR** (euro short-term rate) is the unsecured overnight wholesale borrowing rate of euro-area banks. The ECB publishes it every TARGET2 business day at 08:00 CET as the volume-weighted mean of the previous day's fixed-rate deposits above €1 million reported in the money market statistical reporting (MMSR), after trimming the top and bottom 25% of the volume. Recommended in 2018 as the euro risk-free rate, it started on 2 October 2019 and is hard to manipulate because it comes from real transactions. It tracks the ECB deposit facility rate and is the floating rate of euro OIS, the discount rate of collateralized euro derivatives, and the base of the compounded and term rates that serve as EURIBOR fallbacks. Loans and bonds still mostly use EURIBOR, while €STR is used mainly in short-dated products such as repos and deposits.

### Repo Rates

TODO

## Reference Rates

A **reference rate** is a benchmark rate published daily by an administrator or a central bank. Its main uses are:

- **Floating-rate loans and bonds.** Mortgages, corporate loans and floating-rate notes pay the reference rate, observed again on each reset date, plus a spread for the credit risk of the borrower.
- **Interest rate derivatives.** Swaps, FRAs, futures, caps and floors compute their floating payments from it.
- **Discounting.** Collateralized derivatives are discounted with overnight indexed swap (OIS) rates, because cash collateral earns the overnight rate.
- **Credit spreads.** Risky bond yields are quoted as a spread over a Treasury or swap rate.
- **Monetary policy.** Central banks steer the overnight rate (the Fed with a target range for the federal funds rate, the ECB with its deposit facility rate), and the change passes to all other rates.

To resist manipulation, a reference rate should be anchored in real transactions. LIBOR came from bank estimates, so the market replaced it with transaction-based overnight rates. EURIBOR was reformed instead, and since 2019 a hybrid methodology uses panel-bank transactions when available and data derived from transactions otherwise. It remains the main rate for floating-rate loans and mortgages in the euro area, next to €STR.

## Liquidity preference theory

TODO Explain upward rates