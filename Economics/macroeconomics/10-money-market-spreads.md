# Money Market Spreads

The fixed rate of an overnight indexed swap (OIS) is the expected average of the overnight rate over the life of the swap, with no bank credit risk and no premium for term liquidity (see [From LIBOR to SOFR and OIS](09-from-libor-to-sofr-and-ois.md)). This makes it a clean base for other money market rates. The spread between two rates of the same maturity shows what the market expects and what it charges for each risk, and so how healthy the financial system is.

## How a Spread Isolates One Component

A money market rate contains several components, such as the expected overnight rate, a premium for term liquidity and a premium for credit risk. To study one component, take a rate that contains it and subtract a second rate that contains all the other components but not that one. The common components cancel, and the spread keeps only the component under study.

The same method can isolate the expected path of the policy rate, the credit risk of banks, a liquidity premium or the price of safety. It works only if the content of each rate is clear. If one of the two rates contains a component that the analyst has missed, the spread measures something else (see [Convenience Premium](11-convenience-premium.md)).

## OIS Minus the Overnight Rate

The three-month OIS rate is the expected average of the overnight rate over the next three months. If the market expects no change in policy, this average equals the overnight rate of today, and the spread between the two rates is zero. The spread opens only when the market expects the central bank to move, so it shows what the market expects for the overnight rate.

- **Expected cuts.** The OIS rate falls below the overnight rate, and the spread is negative. In the US this happened before the cuts of 2008, such as the emergency cut of half a point on 8 October 2008, which the Fed announced together with other central banks. It also happened before the first cut of the 2019 cycle, on 31 July 2019, and in August 2024, before the cut of 18 September 2024.
- **Expected hikes.** The OIS rate rises above the overnight rate, and the spread is positive, as in the hiking cycles that began in June 2004, December 2015 and March 2022. In July 2022, for example, the Fed raised its target by 0.75 points for the second time in a row, and the market expected more.
- **No room to fall.** From December 2008 to December 2015 and from March 2020 to March 2022, the target range for the federal funds rate was 0 to 0.25%. Rates could not fall further and the market expected no hike for months, so the spread was about zero.

The diagram in [From LIBOR to SOFR and OIS](09-from-libor-to-sofr-and-ois.md) shows the case of an expected rise, where the fixed rate starts above the overnight rate.

This spread is clean because neither rate contains credit risk or a premium for term liquidity. A spread between the OIS rate and the yield of a three-month bank bond or term deposit would also contain these premiums, so it could not isolate the expected path of the overnight rate.

## OIS After LIBOR

The end of LIBOR changed the instruments that hedge interest rate risk. In April 2025, OIS made up 65% of the global turnover of over-the-counter interest rate derivatives, up from 42% in April 2022. In the currencies that use only overnight risk-free rates, such as the US dollar, sterling, the Swiss franc and the Canadian dollar, they made up more than 90% of swap turnover. Forward rate agreements (FRAs), contracts that lock in an interest rate for one future period, hedged the fixings of LIBOR, and their turnover in US dollars, sterling and yen has virtually disappeared. Euro FRAs, about 80% of global FRA turnover in 2025, survive because Euribor survives.

The market is now anchored to overnight rates, which are much less sensitive to bank credit risk and bank funding costs than LIBOR was. The benchmark is more robust, but it no longer shows the premium for term liquidity and the bank credit risk that the LIBOR–OIS spread measured. The rate of commercial paper (CP) can take the place of LIBOR in that spread.

## The CP–OIS Spread

The rate of three-month AA financial CP shows what a highly rated bank or other financial firm actually pays to borrow for three months without collateral (see [Unsecured Money Market](08-unsecured-money-market.md)). The three-month OIS rate is the expected overnight rate for the same period, with no credit or liquidity premium. The CP–OIS spread is what remains, which is the compensation that the market demands for the liquidity risk and the credit risk of lending to banks.

A wider spread shows tighter funding for banks and can warn of problems in the financial sector. Much economic activity depends on bank credit, so the spread can also warn of a slowdown.

The spread jumped in August 2007. On 9 August, BNP Paribas halted withdrawals from three funds that held US mortgage-backed securities, and in that month the three-month rate of AA financial CP rose from about the effective federal funds rate (EFFR) to a median of 32 bp above it. The spread peaked after the failure of Lehman Brothers, and in October 2008 one-month AA financial CP paid an average of 188 bp over OIS. It widened a little during the euro area debt crisis of 2011, and more before the money market fund reform of October 2016, which cut the demand of prime funds for bank paper. In March 2020 it jumped again, and on 26 March three-month A1/P1 financial CP paid 242 bp over OIS.

### Across Currencies in 2023

In March 2023, Silicon Valley Bank and other US banks failed (see [Matched Book and the September 2019 Repo Spike](07-matched-book-and-the-september-2019-repo-spike.md)), and on 13 March the Bank of England sold the UK subsidiary of Silicon Valley Bank to HSBC. From April to August 2023, the CP–OIS spread of bank paper was positive in US dollars and sterling, about zero in euros and negative in yen.

- **Dollar and sterling.** These were the currencies of the banks in trouble, and policy rates had risen and bank reserves had fallen. Liquidity commanded a premium, and lower-rated paper paid more than top-rated paper as compensation for credit risk.
- **Euro.** Liquidity was still abundant, and the spread was about the same for all ratings.
- **Yen.** Investors even accepted a yield below OIS to place their cash in bank paper.

A negative spread seems to say that an unsecured loan to a bank costs less than the risk-free rate. The Treasury bill explains this puzzle (see [Convenience Premium](11-convenience-premium.md)).

## Commercial Paper Spreads

The CP–OIS spread mixes two risks, liquidity and credit. Spreads between two kinds of CP can separate them. Daily rates exist for 90-day paper of four kinds, which are AA nonfinancial, AA financial, A2/P2 nonfinancial and AA asset-backed. AA paper comes from programs with only top short-term ratings (1 or 1+), and A2/P2 paper from programs with only second-tier ratings (2). Two rates of the same maturity cancel the liquidity premium, and two rates of the same rating cancel the general credit risk.

| Spread of 90-day paper | Same in both rates | Different | Measures |
| --- | --- | --- | --- |
| AA financial minus AA nonfinancial | Maturity and rating | Bank or company | Premium for being a bank |
| A2/P2 minus AA nonfinancial | Maturity and type of issuer | Rating | Price of credit risk |
| AA asset-backed minus AA financial | Maturity and rating | Vehicle or bank | Premium for an off-balance-sheet structure |

### Financial Minus Nonfinancial Paper

This spread keeps only the premium that the market charges a bank for being a bank. In normal times this premium is almost nothing, with a median of 3 bp from 1997 to 2026, so the market lends to an AA bank on the same terms as to an AA company. In the crisis, the spread averaged 115 bp in October 2008 and reached 200 bp on 8 October.

In 2020 the spread turned negative, with an average of −13 bp in May, because the support of the Fed reached the banks first. On 15 March the Fed cut its discount rate to 0.25% and offered banks loans of up to 90 days, and in March it also opened a facility for money market funds, which are large buyers of bank paper. The CPFF bought its first CP only on 14 April. For a few months, a bank thus borrowed more cheaply than a company with the same rating.

The spread reacts to financial crises more than to recessions. In 2001, a year of recession, its median was 2 bp. It is therefore more useful to investors than to economists who follow the business cycle.

### Lower-Rated Minus Top-Rated Paper

Both rates are for paper of nonfinancial companies, so only the rating differs, and the spread is the price of credit risk. Its monthly average has never been below zero, because a riskier issuer always pays more than a safer one, and the question is how much more. When markets are calm, credit spreads fall. When markets come under stress, investors run to quality and the spread jumps.

A rising spread thus warns of financial and economic trouble ahead. A very low spread is also a warning sign, because long periods of prosperity lead borrowers and lenders to take on more risk, as the financial instability hypothesis of Hyman Minsky describes. Both signals are best read together with other indicators.

The spread responded to the three kinds of episode that matter here. Around the recession of 2001, its monthly average rose to 83 bp in February and to 92 bp in November. In the financial crisis, it averaged 455 bp in December 2008. In the liquidity shock of 2020, it averaged 111 bp in March and 115 bp in April.

### Asset-Backed Minus Financial Paper

Asset-backed commercial paper (ABCP) is issued by special purpose vehicles, or conduits, that buy assets such as trade receivables, auto loans, credit card receivables and mortgages and fund them with CP (see [Unsecured Money Market](08-unsecured-money-market.md)). At its peak in 2007, ABCP was more than half of US CP outstanding. A bank usually sets up the conduit but keeps it off its balance sheet. Like a bank, the conduit funds assets of three to five years with short-term paper, but it has no access to the Fed, so when it cannot renew its paper, it relies on guarantees from its sponsor. These guarantees reduced the capital that the banks had to hold, but they gave investors recourse to the banks, and in the crisis most of the losses of the conduits stayed with the sponsor banks.

Both rates are for 90-day paper rated AA, so the spread compares what a bank pays with what its off-balance-sheet vehicle pays. In normal times there is almost no difference, with a median of 6 bp since 2001. In August 2007 the monthly median jumped to 33 bp, and in September to 51 bp, with a daily high of 90 bp on 10 September. The recession began after the peak of December 2007, so the spread moved four months earlier. It fell back during most of 2008 and jumped again to a monthly median of 78 bp in October 2008.

In March 2020 the monthly median was only 7 bp. The shock of 2020 was a general rush for liquidity, not a crisis of solvency in the financial system as in 2008, and this spread helps to tell the two apart.

## References

- Acharya, Viral V., Philipp Schnabl, and Gustavo Suarez. 2013. "Securitization without Risk Transfer." *Journal of Financial Economics* 107 (3): 515–536. [NBER working paper](https://www.nber.org/papers/w15730).
- Adrian, Tobias, Karin Kimbrough, and Dina Marchioni. 2011. "The Federal Reserve's Commercial Paper Funding Facility." *Economic Policy Review* 17 (1), Federal Reserve Bank of New York, May 2011, 25–39. [PDF](https://www.newyorkfed.org/medialibrary/media/research/epr/11v17n1/1105adri.pdf).
- Aquilina, Matteo, Andreas Schrimpf, and Karamfil Todorov. 2023. "CP and CDs Markets: A Primer." *BIS Quarterly Review*, September 2023, 63–76. [Online](https://www.bis.org/publ/qtrpdf/r_qt2309e.htm).
- Bank for International Settlements. 2023. "Bank CP Rates amid Asymmetric Funding-Liquidity Conditions across Currencies." Box in *BIS Quarterly Review*, September 2023. [Online](https://www.bis.org/publ/qtrpdf/r_qt2309y.htm).
- Bank of England. 2023. "Statement on Silicon Valley Bank." 13 March 2023. [Online](https://www.bankofengland.co.uk/news/2023/march/statement-on-silicon-valley-bank).
- Board of Governors of the Federal Reserve System. "About Commercial Paper." Rating categories of the commercial paper rates. [Online](https://www.federalreserve.gov/releases/cp/about.htm).
- Board of Governors of the Federal Reserve System. "Commercial Paper Rates and Outstanding Summary." Daily rates of 90-day AA nonfinancial, A2/P2 nonfinancial, AA financial and AA asset-backed paper, 1997 to November 2026. [Online](https://www.federalreserve.gov/releases/cp/).
- Board of Governors of the Federal Reserve System. "Money Market Mutual Fund Liquidity Facility." [Online](https://www.federalreserve.gov/monetarypolicy/mmlf.htm).
- Board of Governors of the Federal Reserve System. "Open Market Operations." Changes in the target for the federal funds rate. [Online](https://www.federalreserve.gov/monetarypolicy/openmarket.htm).
- Board of Governors of the Federal Reserve System. "Selected Interest Rates (Daily) – H.15." Effective federal funds rate, 1997 to November 2026. [Online](https://www.federalreserve.gov/releases/h15/).
- Board of Governors of the Federal Reserve System. 2020. "Federal Reserve Actions to Support the Flow of Credit to Households and Businesses." Press release, 15 March 2020. [Online](https://www.federalreserve.gov/newsevents/pressreleases/monetary20200315b.htm).
- Boyarchenko, Nina, Richard Crump, and Anna Kovner. 2020. "The Commercial Paper Funding Facility." *Liberty Street Economics*, Federal Reserve Bank of New York, 15 May 2020. [Online](https://libertystreeteconomics.newyorkfed.org/2020/05/the-commercial-paper-funding-facility/).
- Ehlers, Torsten, and Karamfil Todorov. 2025. "Goodbye Libor, Hello Basis Traders: Unpacking the Surge in Global Interest Rate Derivatives Turnover." *BIS Quarterly Review*, December 2025. [Online](https://www.bis.org/publ/qtrpdf/r_qt2512c.htm).
- Minsky, Hyman P. 1992. "The Financial Instability Hypothesis." Working Paper 74, The Jerome Levy Economics Institute of Bard College, May 1992. [PDF](https://www.levyinstitute.org/pubs/wp74.pdf).
- National Bureau of Economic Research. "US Business Cycle Expansions and Contractions." [Online](https://www.nber.org/research/data/us-business-cycle-expansions-and-contractions).
