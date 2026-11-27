# Cross-Currency Basis

Covered interest parity held almost exactly until the crisis of 2007–08 and has failed ever since (see [Interest Rate Parity and Overshooting](21-interest-rate-parity-and-overshooting.md)). This note explains how it fails, why the failure does not disappear and what moves it.

## Two Ways to Borrow Dollars

Suppose that a European bank needs dollars for one year, for example because it has bought US bonds. It can get them in two ways.

1. **Directly.** It borrows dollars, for example by issuing commercial paper in the United States (see [Unsecured Money Market](08-unsecured-money-market.md)).
2. **Through a swap.** It borrows euros, its own currency, and swaps them into dollars. It sells the euros spot today and commits to buy them back in one year at the forward rate, so it bears no exchange rate risk.

Covered interest parity rests once more on arbitrage. Once the gains from arbitrage are exhausted, the bank must be indifferent between the two ways, or there would be free money on the table. The forward rate must therefore differ from the spot rate by exactly the interest differential. With a spot rate of 0.90 euros per dollar, a euro rate of 2% and a dollar rate of 4%, the forward rate for one year is about 0.8827 euros per dollar. Each currency is collateral for the other, so the swap is a secured loan, like a repo whose collateral is another currency (see [Foreign Exchange as a Funding Market](22-foreign-exchange-as-a-funding-market.md)).

## The Basis

Since the crisis the two ways no longer cost the same, and the difference between them is the cross-currency basis. Suppose that the market quotes the forward rate $F$ at 0.880 euros per dollar instead of 0.8827. The bank borrows euros at the rate $i$ of 2%, sells them at the spot rate $S$ of 0.90 and buys them back at 0.880, so the swap gives it dollars at a rate $i^{\text{swap}}$ of about 4.32%.

$$1 + i^{\text{swap}} = (1 + i) \frac{S}{F} = 1.02 \times \frac{0.90}{0.880} \approx 1.0432$$

Borrowed directly, at the rate $i^\ast$, the dollars would cost 4%. Through the foreign exchange market they cost 0.32 percentage points, or 32 basis points, more. This difference, with a negative sign, is the basis.

$$\text{basis} = i^\ast - i^{\text{swap}} \approx 0.04 - 0.0432 = -0.0032$$

Since 2007 the basis against most currencies, notably the euro and the yen, has been negative, so borrowing dollars through swaps has cost more than borrowing them directly.

## The Arbitrage

An arbitrageur takes the opposite position. It borrows dollars directly at 4%, swaps them into euros and lends the euros at 2%, and at maturity it buys the dollars back at the forward rate of 0.880.

| Step | Today | In one year |
| --- | --- | --- |
| Borrow dollars at 4% | Receives $1,000,000 | Repays $1,040,000 |
| Sell the dollars spot at 0.90 | Pays $1,000,000, receives €900,000 | |
| Lend the euros at 2% | Pays €900,000 | Receives €918,000 |
| Buy the dollars forward at 0.880 | | Pays €918,000, receives $1,043,182 |
| Net | 0 | +$3,182 |

The arbitrageur earns $3,182, or 0.32%, without any exchange rate risk, because the forward fixes the rate at which it buys back the dollars. With enough arbitrageurs, the basis should vanish within minutes. It has not. Before 2007 the three-month basis was very close to zero for all the G10 currencies. Covered parity broke in the crisis of 2007–08, and the deviation has persisted since, with an average absolute size of 24 basis points at three months and 27 at five years from 2010 to 2016. Long-term bases peaked during the euro crisis in 2012, narrowed in 2013 and early 2014 and widened again from the second half of 2014.

## Why the Basis Persists

In theory arbitrage is free and unlimited. In the real world banks do it, and their balance sheets have financial and regulatory limits. The arbitrage above borrows dollars from one party and lends euros to another, so the balance sheet of the bank grows on both sides. After 2008 every euro of balance sheet consumed capital, mainly because of regulation. The leverage ratio requires capital against all exposures, whatever their risk, so it treats an almost riskless arbitrage like a risky loan (see [Modern Money Creation](04-modern-money-creation.md)). With capital of 3% of the exposures and shareholders who ask for a return of 10% a year, a bank needs a basis of at least 3% × 10% = 0.3%, or 30 basis points, before the arbitrage pays. The 32 basis points of the example barely cover it. If the gain does not pay for the balance sheet, nobody arbitrages, and the basis stays. A large demand for dollars through swaps, for example to hedge dollar assets, opens the basis, and the limits to arbitrage stop it from closing.

The basis can therefore be read as the shadow price of the balance sheet capacity of banks, or as the price of poor regulation. It widens at the end of each quarter, when many banks report their balance sheets to supervisors and do not want them to look large. Since January 2015, European banks have computed their leverage ratio from the balance sheet on the last day of the quarter, and the basis of one-week contracts that cross the end of a quarter has risen by another 30 to 40 basis points on average.

Another reading is that, before 2008, swaps were priced at covered parity because liquidity was taken to be a free or nearly free good. For Mehrling, this assumption "turned out to be an idealization, not a fact about the world". The crisis of 2008 forced the market to put a price on liquidity in foreign currency, and that price is the basis. Whatever the reading, regulation, balance sheet capacity or the price of liquidity, the basis needs an explanation.

## A Thermometer of Dollar Funding

The level of the basis works as a thermometer of the payment imbalances of the global system. Under stress, when everyone wants dollars at the same time, dollars through the back door of the swap become very expensive, and the basis becomes more negative. The three-month basis of the euro reached about −330 basis points in early October 2008, after the failure of Lehman Brothers, and about −150 in November 2011, during the euro crisis. In mid-March 2020 it reached −85 basis points for the euro and about −150 for the yen, and it was worse for some currencies whose central bank had no swap line with the Fed.

In these episodes the swap lines of the Fed put a limit on the basis. When the price of dollars in the private market came close to the price of the swap line, banks stopped borrowing in the market and borrowed from their central bank instead. On 30 November 2011, when the central banks announced that the price of the swap lines would fall to the OIS rate plus 50 basis points, the swap spreads above 50 basis points came down at once, and the premium for swapping euros into dollars fell from 151 to 119 basis points. This is the outside spread of the dealer of last resort (see [International Hierarchy of Money](23-international-hierarchy-of-money.md)), applied to the basis.

## The Dollar Moves the Basis

What explains the basis best is not some odd variable of the swap market but the exchange rate of the dollar. The relationship forms a triangle.

- When the dollar strengthens, deviations from covered parity grow, so the basis becomes more negative, and banks lend fewer dollars across borders.
- When the dollar weakens, the opposite happens.

From 2007 to early 2016, a single common factor explained 53% of the quarterly changes in the five-year basis of ten G10 currencies against the dollar. Its correlation with the changes in the broad dollar index of the Fed, which averages the value of the dollar against the currencies of 26 economies weighted by their trade with the United States, was −0.75. The value of the dollar thus works as a barometer of the capacity of global capital markets to take risk.

## The Risk-Taking Channel of the Dollar

Suppose that a Chilean company sells in pesos but has borrowed $1 million, because dollars were cheaper. At 900 pesos per dollar, the debt is worth 900 million pesos. If the dollar rises by 5%, to 945 pesos, the debt grows, while the assets in pesos are worth the same.

| | 900 pesos per dollar | 945 pesos per dollar |
| --- | --- | --- |
| Assets, in pesos | 1,000 million | 1,000 million |
| Debt of $1 million, in pesos | 900 million | 945 million |
| Equity, in pesos | 100 million | 55 million |

A rise of 5% in the dollar cuts the equity of the company by 45%, although the company has done nothing to deserve it. The bank that lends to it watches its risk and sees that the loans are now riskier, with less capital behind them. With the same capital, the bank can take less risk, so it lends fewer dollars and charges more for those that it still lends, including the dollars that it lends through swaps. The basis becomes more negative. When the dollar depreciates, everything works the other way. The balance sheets of those who owe dollars improve, banks have spare capacity, they lend more, and the basis narrows. This is the risk-taking channel of monetary policy (see [Transmission Channels and Pass-Through](14-transmission-channels-and-pass-through.md)), with the exchange rate of the dollar in the place of the policy rate.

The pattern is the hierarchy of money at a world scale (see [Credit and Currency](03-credit-and-currency.md)). In an expansion, the hierarchy flattens and dollars are easy to get. In a contraction, it steepens and dollars become expensive.

## Two Channels in Opposite Directions

In the market for goods, a weaker currency makes exports cheaper, at least in the short run, which gives the economy a temporary boost (see [Exchange Rates and Purchasing Power Parity](19-exchange-rates-and-purchasing-power-parity.md)). The financial channel works the other way. For a country with much debt in dollars, an appreciation against the dollar eases its financial conditions, and a depreciation tightens them. The two channels work at the same time and in opposite directions. In emerging economies the financial channel offsets part of the trade channel, more so the more debt they have in foreign currency, and in some cases a depreciation could even contract the economy. A devaluation is therefore not clearly a good idea, even in the short run.

## A Vicious Circle

The dollar moves the basis, and the basis exists because the balance sheets of intermediaries cannot arbitrage every difference. Dealers in the foreign exchange market also move the price when their book stops being matched (see [Foreign Exchange as a Funding Market](22-foreign-exchange-as-a-funding-market.md)). A currency crisis can therefore feed on itself.

1. The dollar strengthens.
2. The balance sheet capacity of banks shrinks.
3. Dollars become scarcer.
4. Scarcer dollars strengthen the dollar again.

In this view, a currency crisis comes from the balance sheets of intermediaries more than from the market for goods. The circle needs something to start it, however, such as an imbalance that moves the exchange rate, and that something can come from the market for goods. The financial view and the theories of goods and money (see [Exchange Rates and Purchasing Power Parity](19-exchange-rates-and-purchasing-power-parity.md) and [Balance of Payments and the Monetary Approach](20-balance-of-payments-and-the-monetary-approach.md)) therefore complement each other.

## References

- Avdjiev, Stefan, Wenxin Du, Cathérine Koch, and Hyun Song Shin. 2019. "The Dollar, Bank Leverage, and Deviations from Covered Interest Parity." *American Economic Review: Insights* 1 (2): 193–208. [DOI](https://doi.org/10.1257/aeri.20180322).
- Baba, Naohiko, and Frank Packer. 2009. "From Turmoil to Crisis: Dislocations in the FX Swap Market Before and After the Failure of Lehman Brothers." BIS Working Papers 285, July 2009. [Online](https://www.bis.org/publ/work285.htm).
- Bahaj, Saleem, and Ricardo Reis. 2022. "Central Bank Swap Lines: Evidence on the Effects of the Lender of Last Resort." *Review of Economic Studies* 89 (4): 1654–1693. [DOI](https://doi.org/10.1093/restud/rdab074).
- Board of Governors of the Federal Reserve System. "Foreign Exchange Rates – H.10. Currency Weights." [Online](https://www.federalreserve.gov/releases/h10/weights/).
- Borio, Claudio, Robert N. McCauley, Patrick McGuire, and Vladyslav Sushko. 2016. "Covered Interest Parity Lost: Understanding the Cross-Currency Basis." *BIS Quarterly Review*, September 2016, 45–64. [Online](https://www.bis.org/publ/qtrpdf/r_qt1609e.htm).
- Bruno, Valentina, and Hyun Song Shin. 2015. "Capital Flows and the Risk-Taking Channel of Monetary Policy." *Journal of Monetary Economics* 71: 119–132. [DOI](https://doi.org/10.1016/j.jmoneco.2014.11.011).
- Bruno, Valentina, and Hyun Song Shin. 2015. "Cross-Border Banking and Global Liquidity." *Review of Economic Studies* 82 (2): 535–564. [DOI](https://doi.org/10.1093/restud/rdu042).
- Du, Wenxin, Alexander Tepper, and Adrien Verdelhan. 2018. "Deviations from Covered Interest Rate Parity." *Journal of Finance* 73 (3): 915–957. [DOI](https://doi.org/10.1111/jofi.12620).
- Eren, Egemen, Andreas Schrimpf, and Vladyslav Sushko. 2020. "US Dollar Funding Markets During the Covid-19 Crisis – the International Dimension." BIS Bulletin 15, 12 May 2020. [Online](https://www.bis.org/publ/bisbull15.htm).
- Kearns, Jonathan, and Nikhil Patel. 2016. "Does the Financial Channel of Exchange Rates Offset the Trade Channel?" *BIS Quarterly Review*, December 2016, 95–113. [Online](https://www.bis.org/publ/qtrpdf/r_qt1612i.htm).
- Mehrling, Perry. 2015. "Elasticity and Discipline in the Global Swap Network." *International Journal of Political Economy* 44 (4): 311–324. [DOI](https://doi.org/10.1080/08911916.2015.1129848).
- Shin, Hyun Song. 2016. "Global Liquidity and Procyclicality." Speech at the World Bank conference "The State of Economics, the State of the World", Washington DC, 8 June 2016. [Online](https://www.bis.org/speeches/sp160608.htm).
- Vause, Nicholas, and Goetz von Peter. 2011. "Euro Area Sovereign Crisis Drives Global Financial Markets." *BIS Quarterly Review*, December 2011, 1–14. [Online](https://www.bis.org/publ/qtrpdf/r_qt1112a.htm).
