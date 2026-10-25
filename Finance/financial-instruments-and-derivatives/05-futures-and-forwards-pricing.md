# Futures and Forwards Pricing

Arbitrage arguments give the forward and futures prices of an investment asset from its spot price and other observable market variables. This is not possible for consumption assets, for reasons explained later.

The pricing equations below assume that some market participants:

1. Pay no transaction costs when they trade.
2. Pay the same tax rate on all net trading profits.
3. Borrow and lend at the same risk-free rate.
4. Take advantage of arbitrage opportunities as they occur.

These assumptions do not need to hold for all market participants, only for a few key ones such as large derivatives dealers. The trading of these key participants, and their eagerness to exploit arbitrage, sets the relationship between forward and spot prices.

## Short Selling

**Short selling** is the sale of an asset that the investor does not own. The broker borrows the asset from another client and sells it in the market. To close the position, the investor buys the asset back and returns it to the lender. The investor gains if the price falls and loses if it rises, with no upper limit on the loss.

While the position is open, the investor pays the lender any income from the asset, such as dividends or coupons. The broker holds a **margin account** as collateral, charges a fee to borrow the asset, and can force the position to close if the lender recalls the asset.

Some arbitrage strategies start with the sale of an asset, so they require the arbitrageur to hold the asset beforehand. Short selling usually removes this requirement, at the cost of the **borrowing fee**.

Short selling is not always available, but investors who hold the asset purely for investment can still do these trades. They sell the asset instead of borrowing it, and at the end of the strategy they hold the same asset plus the profit.

## Future and Forward Price of an Investment Asset

In the case of investment assets we consider three different situations, the asset provides no income, the asset provides known dollar income, the asset provides known yield.

The pricing equations use the following notation.

- $T$ is the time to the delivery date of the contract, in years.
- $S_0$ is the price of the underlying asset today.
- $F_0$ is the forward or futures price today.
- $r$ is the risk-free zero rate for the maturity $T$, per annum with continuous compounding.

### No Income Asset

The simplest forward contract to price is one on an investment asset that provides no income and has no storage costs, such as a non-dividend-paying stock or a zero-coupon bond.

Under no arbitrage, the forward price is

$$F_0 = S_0 e^{rT}$$

If $F_0 > S_0 e^{rT}$, the forward is overpriced. An arbitrageur borrows $S_0$ at $r$, buys the asset, and takes a short forward position. At $T$, the arbitrageur delivers the asset for $F_0$ and repays $S_0 e^{rT}$, for a profit of

$$F_0 - S_0 e^{rT} > 0$$

If $F_0 < S_0 e^{rT}$, the forward is underpriced. An arbitrageur short sells the asset, invests $S_0$ at $r$, and takes a long forward position. At $T$, the arbitrageur receives $S_0 e^{rT}$, buys the asset for $F_0$, and returns it to the lender, for a profit of

$$S_0 e^{rT} - F_0 > 0$$

Arbitrageurs exploit either gap until the trades push $F_0$ back to $S_0 e^{rT}$.

### Known Income Asset

The asset provides an income with a known present value $I$ during the life of the contract, such as a coupon-bearing bond or a stock with known dividends. $I$ is the sum of the income payments, each discounted at the risk-free rate.

Under no arbitrage, the forward price is

$$F_0 = (S_0 - I) e^{rT}$$

The income lowers the forward price, because the holder of the asset receives it and the holder of the forward does not.

If $F_0 > (S_0 - I) e^{rT}$, the forward is overpriced. An arbitrageur borrows $S_0$ at $r$, buys the asset, and takes a short forward position. The income repays part of the loan when it arrives. At $T$, the arbitrageur delivers the asset for $F_0$ and repays the remaining $(S_0 - I) e^{rT}$, for a profit of

$$F_0 - (S_0 - I) e^{rT} > 0$$

If $F_0 < (S_0 - I) e^{rT}$, the forward is underpriced. An arbitrageur short sells the asset, invests $S_0$ at $r$, and takes a long forward position. Part of the investment pays the income owed to the lender of the asset. At $T$, the arbitrageur receives the remaining $(S_0 - I) e^{rT}$, buys the asset for $F_0$, and returns it to the lender, for a profit of

$$(S_0 - I) e^{rT} - F_0 > 0$$

Arbitrageurs exploit either gap until the trades push $F_0$ back to $(S_0 - I) e^{rT}$.

### Known Yield Asset

## Forward Contracts Valuation


### Considering Daily settlement, Futures vs Forwards

With a constant risk-free rate, forward and futures prices for the same delivery date can be considered equal. Daily settlement only changes the timing of the cash flows. With a known rate, an investor can scale the futures position each day so that the settled gains, plus interest, match the payoff of a forward at maturity. Both strategies cost nothing to enter and pay the same, so the two prices must be equal.

With unpredictable interest rates, the timing matters and the two prices differ. Suppose the asset price correlates positively with interest rates. When the price rises, a long futures position receives cash at once and invests it at a rate that is likely high. When the price falls, it pays cash at once and finances the loss at a rate that is likely low. A forward has no cash flows before maturity, so it gets neither benefit. Investors prefer the long futures position, and the futures price is higher than the forward price. With a negative correlation, as for bond futures, the futures price is lower.

For contracts of a few months the difference is negligible, so this note treats the two prices as equal. For long-dated contracts the interest on the daily cash flows compounds and the difference can become large. Taxes, transaction costs, margin treatment, and the lower default risk of futures can also make the prices differ.

## Forward and Futures Contracts on Currencies

## Forward Price of a Commodity

## Cost of Carry

## Futures Prices and Expected Future Spot Price