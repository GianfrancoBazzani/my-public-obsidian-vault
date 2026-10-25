# Markets, Assets, and Types of Traders

## Exchange-traded vs. over-the-counter markets

An **exchange-traded market** is a centralized, organized marketplace (such as the CME Group or Eurex) where standardized contracts are traded. The exchange defines the contract terms, such as the underlying asset, the contract size, and the delivery or expiration dates. Trades go through a clearing house, which stands between buyer and seller and requires margin from both, so counterparty credit risk is greatly reduced. Prices and trading volumes are publicly visible. Futures contracts trade on exchanges, while forward contracts trade OTC (see [Futures and Forwards](04-futures-and-forwards.md) for the comparison of the two contracts).

The **over-the-counter (OTC) market** is a decentralized network in which participants, typically banks, other financial institutions, fund managers, and corporations, deal directly with one another, traditionally by phone and now increasingly through electronic platforms. Because each deal is negotiated privately, contracts can be customized to fit the parties' exact needs, such as an unusual maturity, notional amount, or underlying asset. The trade-off is that OTC transactions have historically carried more counterparty credit risk and less transparency. Since the 2008 financial crisis, regulators have narrowed this gap by requiring many standardized OTC derivatives to be cleared through central counterparties and reported to trade repositories.

**Bid and offer quotes of a market maker**

In the OTC market, large financial institutions often act as market makers. A market maker stands ready to trade with clients and quotes two prices at the same time, a bid and an offer.

The **bid** is the price at which the market maker is prepared to *buy*. The **offer** (also called the **ask**) is the price at which the market maker is prepared to *sell*.

The offer is always higher than the bid. The difference between them, the **bid–offer spread**, is how the market maker earns a profit and is compensated for the risk of holding positions. For example, a dealer quoting a currency at 1.0850 / 1.0852 will buy at 1.0850 and sell at 1.0852. A client who wants to sell receives the lower price, and a client who wants to buy pays the higher one.

## Types of orders

An order tells the broker how to execute a trade. The main types are the following.

| Order                                        | Meaning                                                                                                                                                  |
| -------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Market order                                 | Trade immediately at the best available price.                                                                                                          |
| Limit order                                  | Trade only at a specified price or at a price more favorable to the trader.                                                                              |
| Stop order (stop-loss order)                 | When a bid or offer reaches the specified price or a worse one, the order becomes a market order.                                                       |
| Stop-limit order                             | When the stop price is reached, the order becomes a limit order. The order therefore needs two prices, the stop price and the limit price.               |
| Market-if-touched (MIT) order (board order)  | When a trade occurs at the specified price or a more favorable one, the order becomes a market order. Traders use it to take profits after favorable moves. |
| Discretionary order (market-not-held order)  | A market order that the broker can delay to try to get a better price.                                                                                   |

## Types of traders

In the market we can identify three types of traders, the hedgers, the speculators and the arbitrageurs.

**Hedgers** use derivatives to **reduce risk** they already face. Forwards and futures lock in a future price, which removes uncertainty but also gives up favourable moves. Options act like insurance, because they protect against bad moves and keep the upside, for an upfront premium. Hedging makes outcomes more certain, not necessarily better.

**Speculators** **take on risk** by betting on price direction, with no exposure to protect. Derivatives give them **leverage**. Futures need only a small margin, and options buy more exposure per dollar. For example, 2,000 USD in call options can earn far more than 2,000 USD in shares, or be lost entirely. Leverage magnifies both gains and losses.

**Arbitrageurs** lock in a **riskless profit** through simultaneous trades in two or more markets, exploiting price differences. An example is buying a stock cheaply in New York and selling it higher in London. Such opportunities disappear quickly because arbitrage trading closes the gap. The pricing of derivatives relies on the **no-arbitrage** assumption.

| Trader      | Goal                    | Risk   | Existing exposure? |
| ----------- | ----------------------- | ------ | ------------------ |
| Hedger      | Reduce risk             | Avoids | Yes                |
| Speculator  | Profit from price moves | Seeks  | No                 |
| Arbitrageur | Riskless profit         | None   | No                 |

**Drift into speculation**

Hedgers or arbitrageurs can drift into speculating, as in the Barings and Société Générale losses, so firms need strict risk limits.

## Is speculation in futures markets gambling?

A common view holds that speculation in futures markets is pure gambling and that speculators should not be allowed on futures exchanges. The view has some truth in it, but it ignores the role of speculators.

**Why the view looks reasonable**

A speculator has no exposure to protect and takes risk only for profit, so a futures position looks like a bet. Leverage makes the bet larger, and before costs futures trading is a zero-sum game. Large speculative positions can also add volatility or be used to try to corner a market.

**Why the view is wrong**

A casino creates risk for entertainment, while a futures market transfers a risk that already exists. A farmer faces the price of wheat whether an exchange exists or not, and speculators are the traders who accept that risk.

- **Counterparties for hedgers.** A wheat producer who wants to sell forward may not find, on the same day, a miller who wants to buy the same quantity. Speculators fill this gap.
- **Liquidity.** Speculative volume narrows bid–offer spreads, lowers costs for hedgers, and lets large positions trade without a big move in price.
- **Price discovery.** Speculators profit only if they forecast well, so they collect information on supply and demand. Their trades put it into the futures price that producers and consumers use to plan.
- **Compensation for risk.** In theory, hedgers pay speculators a premium for taking their risk, much as an insurer earns a premium, although the evidence for this premium is mixed.

**The public-interest answer**

A ban would make futures markets thin and costly and would hurt the hedgers it means to protect. The real concern is excessive or manipulative speculation, which exchanges and regulators control with the following rules (see [Futures and Forwards](04-futures-and-forwards.md)).

- **Margin requirements** make each trader cover losses daily, so one default does not spread.
- **Daily price limits** cap how far the price can move in one session, which slows panic moves.
- **Position limits** cap the speculative contracts one trader can hold, which makes corners and squeezes harder.
- **Large-trader reporting** lets regulators watch big positions and act against manipulation.

Speculation is therefore a necessary part of a working futures market. It should be regulated, not banned.
