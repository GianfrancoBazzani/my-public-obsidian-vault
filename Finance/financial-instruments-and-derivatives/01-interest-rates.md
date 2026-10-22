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

They are usually lower than other very low-risk rates for two main reasons.

 1. Regulatory demand and capital requirements: Banks and other financial institutions must hold Treasuries to meet regulatory requirements, and they need to set aside less capital for Treasuries than for other low-risk investments. This raises demand for Treasuries, which pushes their prices up and their yields down.
 2. Tax advantages: Interest earned on Treasuries is exempt from state and local income taxes, unlike most other fixed-income investments. Because investors keep more of the return after taxes, they are willing to accept a lower stated rate.
 
### Overnight Rates

Banks hold reserves in accounts at the central bank. At the end of each day some banks have surplus reserves and others need funds, so they lend and borrow overnight, bilaterally or through a broker. Each currency has its own overnight benchmark:

- **€STR** (euro short-term rate) is the unsecured overnight wholesale borrowing rate of euro-area banks. The ECB publishes it every TARGET2 business day at 08:00 CET as the volume-weighted mean of the previous day's fixed-rate deposits above €1 million reported in the money market statistical reporting (MMSR), after trimming the top and bottom 25% of the volume. Recommended in 2018 as the euro risk-free rate, it started on 2 October 2019 and is hard to manipulate because it comes from real transactions. It tracks the ECB deposit facility rate and is the floating rate of euro OIS, the discount rate of collateralized euro derivatives, and the base of the compounded and term rates that serve as EURIBOR fallbacks.
- **EFFR** (effective federal funds rate) is the unsecured overnight rate of the US federal funds market. The New York Fed publishes it at about 09:00 ET on the next business day as the volume-weighted median of the transactions that domestic banks and US branches of foreign banks report on the FR 2420 form. The FOMC sets a target range for it, so it is the policy rate of the Fed, but the USD risk-free rate that replaced LIBOR is the secured SOFR.
- **SONIA** (Sterling Overnight Index Average) is the unsecured overnight sterling rate. The Bank of England has administered it since 2016 and publishes it at 09:00 on the next business day as the volume-weighted mean of the central 50% of the eligible deposits of at least £25 million, brokered or bilateral. Recommended in 2017 as the sterling risk-free rate, it replaced GBP LIBOR.
- **TONA** (Tokyo Overnight Average Rate) is the unsecured overnight call rate in yen. The Bank of Japan publishes it at 10:00 Tokyo time on the next business day as the volume-weighted average of all the transactions that settle on the trade date and mature on the next business day. Recommended in December 2016 as the yen risk-free rate, it replaced JPY LIBOR.
- **SARON** (Swiss Average Rate Overnight) is the secured overnight rate of the Swiss franc repo market. SIX has administered it since 2009 and calculates it from concluded repo trades and binding quotes on the SIX repo platform, with filters against manipulation and a reference fixing at 18:00 Zurich time. Recommended in October 2017 as the Swiss franc risk-free rate, it replaced CHF LIBOR, and since June 2019 the Swiss National Bank (SNB) has steered it close to the SNB policy rate.

### Repo Rates

Unlike unsecured overnight rates, repo rates are secured borrowing rates. In a **repo** (repurchase agreement), a financial institution sells securities, usually government bonds, and agrees to buy them back later at a slightly higher price. The difference between the two prices is the interest, and its annualized value is the **repo rate**. For the counterparty, the same trade is a **reverse repo**. The lender receives legal title to the securities, so if the borrower defaults the lender sells them, and if the lender defaults the borrower keeps the cash, with any difference settled by close-out netting under a master agreement such as the GMRA. A **haircut** (cash lent below the market value of the securities) and daily margin calls protect the lender against a fall in the value of the collateral, so a repo has very little credit risk. Most repos are overnight, and longer ones are **term repos**. **General collateral** (GC) repos accept any bond of a given class, while **special** repos ask for one bond in high demand and pay a lower rate. In theory a repo rate is slightly below the unsecured overnight rate of the same currency, but scarce reserves or a large supply of bonds can push it above, as when SOFR rose above the EFFR from late 2025. The main repo benchmarks are:

- **SOFR** (Secured Overnight Financing Rate) is the overnight rate of repos backed by US Treasuries. The New York Fed publishes it at about 08:00 ET on the next business day as the volume-weighted median of tri-party, GCF and FICC-cleared bilateral transactions, with specials filtered out. Recommended in 2017 as the USD risk-free rate, it replaced USD LIBOR.
- **SARON** (see Overnight Rates) is the Swiss franc equivalent.
- **RepoFunds Rate** is a family of daily repo indices that CME publishes from trades on the BrokerTec and MTS platforms, with RFR Euro and country indices such as RFR Germany for euro sovereign collateral and RFR Sterling for gilts.
- **Tokyo Repo Rate** is the yen repo rate that the Japan Securities Dealers Association (JSDA) publishes for tenors from overnight to one year.

## Reference Rates

A **reference rate** is a benchmark rate published daily by an administrator or a central bank. Its main uses are:

- **Floating-rate loans and bonds.** Mortgages, corporate loans and floating-rate notes pay the reference rate, observed again on each reset date, plus a spread for the credit risk of the borrower.
- **Interest rate derivatives.** Swaps, FRAs, futures, caps and floors compute their floating payments from it.
- **Discounting.** Collateralized derivatives are discounted with overnight indexed swap (OIS) rates, because cash collateral earns the overnight rate.
- **Credit spreads.** Risky bond yields are quoted as a spread over a Treasury or swap rate.
- **Monetary policy.** Central banks steer the overnight rate (the Fed with a target range for the federal funds rate, the ECB with its deposit facility rate), and the change passes to all other rates.

To resist manipulation, a reference rate should be anchored in real transactions. Before LIBOR was retired (end of 2021 for most settings, June 2023 for USD), national working groups chose a nearly risk-free overnight rate (RFR) for each currency to replace it. These rates are calculated from large volumes of real transactions instead of bank estimates, which makes them much harder to manipulate, though not immune. Because they are overnight and carry almost no bank credit risk, contracts compound them over the interest period (in arrears, or through term versions such as Term SOFR) and add a fixed credit spread adjustment when they convert legacy LIBOR deals.

| Currency | Replaces | New rate | Full name | Administrator | Underlying market | Type |
|---|---|---|---|---|---|---|
| USD | USD LIBOR | **SOFR** | Secured Overnight Financing Rate | NY Fed | Treasury repo | Secured |
| EUR | EUR LIBOR / EONIA | **€STR** | Euro Short-Term Rate | ECB | Wholesale bank borrowing | Unsecured |
| GBP | GBP LIBOR | **SONIA** | Sterling Overnight Index Average | Bank of England | Overnight deposits | Unsecured |
| CHF | CHF LIBOR | **SARON** | Swiss Average Rate Overnight | SIX | CHF repo | Secured |
| JPY | JPY LIBOR | **TONA** | Tokyo Overnight Average Rate | Bank of Japan | Uncollateralized call money | Unsecured |

EURIBOR was reformed instead of retired, and since 2019 a hybrid methodology uses panel-bank transactions when available and data derived from transactions otherwise. It remains the main rate for floating-rate loans and mortgages in the euro area, next to €STR.

## Liquidity Preference Theory

The **liquidity preference theory** explains why the yield curve usually slopes upward. Depositors and investors prefer short maturities, because long bonds are less liquid and their prices move more when rates change, so an early sale can bring a larger loss, while borrowers prefer long fixed-rate loans, which remove their refinancing risk. This makes supply and demand asymmetric, with a surplus of short-term funds and a shortage of long-term funds. Banks and other intermediaries close this gap by setting long rates above the expected future short rates, which attracts long-term deposits and discourages long-term borrowing. The extra yield is the **liquidity (term) premium**, so a forward rate equals the expected future short rate plus a premium that usually grows with maturity, and the curve slopes upward even when short rates are expected to stay flat.

In terms of yields, the $n$-year rate is approximately the average of the current and expected one-year rates plus a premium $L_n$ that the theory assumes to be positive and to grow with maturity.

$$i_n = \frac{i_1 + i_2^e + \dots + i_n^e}{n} + L_n$$

The shape of the curve then depends on the expected path of short rates. Expected rises give a steep upward curve, flat expectations still give an upward curve, small expected falls give a flat or upward curve, and only large expected falls give an inverted curve. For example, with a one-year rate of 4% and premiums of 0.25% at two years and 0.50% at three years, the yields are the following.

| Maturity | Short rates expected flat at 4% | Short rates expected to fall to 3% and 2% |
| --- | --- | --- |
| 1 year | 4.00% | 4.00% |
| 2 years | 4% + 0.25% = 4.25% | 3.5% + 0.25% = 3.75% |
| 3 years | 4% + 0.50% = 4.50% | 3% + 0.50% = 3.50% |

This explains why upward curves are much more common than inverted ones, while the pure expectations theory, with no premium, predicts both about equally often.

Banks earn this premium through **maturity transformation**, funding long fixed-rate loans with short deposits, but a rise in short rates then reduces their net interest income, a risk that they manage with asset-liability management and swaps. The theory, formalized by Hicks in 1939, differs from the **expectations theory** (long rates reflect only expected short rates, so forward rates equal expected rates) and the **market segmentation theory** (each maturity has its own supply and demand). The premium is not always positive, and model estimates of the US 10-year term premium were mostly negative from 2016 to 2024 under quantitative easing.