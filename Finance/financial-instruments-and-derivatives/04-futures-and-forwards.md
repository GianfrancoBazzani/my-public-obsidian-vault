# Futures and Forwards

## Long vs. short forwards

A **forward** is an agreement made today to trade an asset on a future date at a fixed delivery price $K$. The long party agrees to buy the asset, and the short party agrees to sell it. Nothing changes hands at the start. The contract is set up to be worth zero to both sides, and the trade happens at maturity.

The terms "long" and "short" describe your side of the contract and which way you benefit from price moves. Long means you'll own the asset, so you gain if the price rises. Short means you'll deliver it, so you gain if the price falls. The difference is defined by the obligation to buy or sell, not by expectations.

At maturity, with $S_T$ as the spot price, the payoffs of the two sides are the following.

$$\text{Long payoff} = S_T - K$$

$$\text{Short payoff} = K - S_T$$

Since there's no upfront cost, payoff equals profit. Both sides are obligated, so the payoffs are straight lines. The long side has unlimited gains and a maximum loss of $K$ if the price falls to zero, and the short side has the opposite.

**Extending to options**

With options, "long" means you bought the option (the holder) and "short" means you sold or wrote it (the writer). The holder has a right, the writer has an obligation, and the holder pays a premium upfront ($c$ for a call, $p$ for a put).

| Position   | Right or obligation             | Profit                 | Gains if               |
| ---------- | ------------------------------- | ---------------------- | ---------------------- |
| Long call  | Right to buy                    | $\max(S_T - K, 0) - c$ | The price rises        |
| Short call | Obligation to sell if exercised | $c - \max(S_T - K, 0)$ | The price stays below $K + c$ |
| Long put   | Right to sell                   | $\max(K - S_T, 0) - p$ | The price falls        |
| Short put  | Obligation to buy if exercised  | $p - \max(K - S_T, 0)$ | The price stays above $K - p$ |

The key difference from forwards is that with options, "long" doesn't always mean buying the asset. A long put gives you the right to sell. Because the holder only exercises when it's profitable, option payoffs are kinked rather than straight. The holder's maximum loss is the premium, while the writer's maximum gain is that premium, with potentially large losses (unlimited for a short call, up to $K - p$ for a short put).

**The zero-sum link**

In both forwards and options, the long's profit plus the short's profit always equals zero, so one side's gain is exactly the other's loss. The premium is the price the option holder pays to replace a forward's obligation with a right. That changes how risk is divided between the two sides, but not the zero-sum total.

## Forwards vs. futures

A **futures contract** is also an agreement to buy or sell an asset on a future date at a price fixed today. The economic idea is the same as a forward, but the two contracts trade in different ways. A forward is a private contract between two parties in the OTC market. A futures contract trades on an exchange, with the standardized terms, the clearing house and the margin of an exchange-traded market (see the section on exchange-traded and OTC markets in [Markets, Assets, and Types of Traders](03-markets-assets-and-type-of-traders.md)).

|                  | Forward                                      | Futures                                           |
| ---------------- | -------------------------------------------- | ------------------------------------------------- |
| Market           | OTC, private between two parties             | Exchange                                          |
| Terms            | Customized                                   | Standardized by the exchange                      |
| Settlement       | One settlement at maturity                   | Daily settlement (marking to market)              |
| Credit risk      | Each side depends on the other side          | Greatly reduced by the clearing house and margin  |
| Delivery date    | Usually one specified date                   | Often a range of dates, chosen by the short side  |
| End of contract  | Usually held to delivery or cash settlement  | Usually closed out before maturity                |

**Daily settlement**

The main practical difference is the timing of the gains and losses. A forward pays the whole gain or loss at maturity. A futures contract pays it at the end of each day, into or out of the margin account of the trader. This is **marking to market**.

The margin is a performance bond. It makes sure that the losers can pay the winners, stops the losses from building up, and protects the broker and the clearing house. Because it is a small part of the value of the contract, it also gives leverage, which magnifies both gains and losses.

- **Initial margin.** The deposit when the position opens, usually a small percentage of the value of the contract.
- **Maintenance margin.** The minimum balance, lower than the initial margin. Below it, the trader receives a margin call.
- **Variation margin.** The funds that the trader adds after a margin call, usually within one day, to bring the balance back to the initial margin. In clearing, the term often means the daily gain or loss. If the trader does not pay, the broker closes the position.

The clearing house of the exchange sets the minimum margins and increases them when the price becomes more volatile, and a broker can ask for more. The trader can withdraw the balance above the initial margin. The margin can be cash or government bills. The bills keep their interest, so their opportunity cost is small, but some brokers pay little or no interest on cash. The traders post margin with their brokers, the brokers with the members of the clearing house, and the members post a **clearing margin** with the clearing house.

**Example**

A trader goes long one futures contract at 100, with an initial margin of 3 ($3\%$ of the value) and a maintenance margin of 2.5. The trader holds it to maturity, where the futures price is equal to the spot price $S_T = 102$.

| Day          | Futures price | Daily gain or loss | Cumulative gain or loss | Margin balance | Variation margin |
| ------------ | ------------- | ------------------ | ----------------------- | -------------- | ---------------- |
| 0            | 100           | -                  | -                       | 3              | -                |
| 1            | 101           | +1                 | +1                      | 4              | -                |
| 2            | 99            | -2                 | -1                      | 2              | +1               |
| 3 (maturity) | 102           | +3                 | +2                      | 6              | -                |

On day 2 the balance falls to 2, below 2.5, so the trader receives a margin call and adds 1. At maturity the balance is 6 for total deposits of $3 + 1 = 4$, a gain of 2, which is the final price minus the initial price. A long forward with $K = 100$ gives the same payoff, $S_T - K = 2$, if we ignore the interest on the margin, but it pays it once at maturity and not day by day.

## Specification of a futures contract

When an exchange creates a new futures contract, it must specify the exact terms of the agreement between the two sides. These standard terms are what make futures contracts interchangeable. The goal of the design is a contract that attracts enough hedgers and speculators to give good liquidity. The main parameters are the following.

- **The asset.** The exchange specifies the underlying asset and, for a commodity, the grades or qualities that the short side can deliver. If the short side delivers a grade other than the standard one, the price receives an adjustment, a premium or a discount.
- **The contract size.** This is the quantity of the asset in one contract. A contract that is too large excludes the small investors and hedgers. A contract that is too small has high trading costs, because each contract has a cost to trade.
- **The delivery arrangements.** The exchange specifies the place of delivery. The place is important when the transport costs are significant, and the price can receive an adjustment for a place other than the standard one.
- **The delivery months.** The exchange specifies the months of the contract and the period in each month when the delivery can occur. Many financial futures use the quarterly cycle of March, June, September and December.
- **The price quotes.** The exchange specifies how it quotes the price and the tick size, which is the minimum movement of the price.
- **The daily price limits.** These are the maximum movements of the price in one day. A movement equal to the limit is a limit move (limit up or limit down). The limits prevent large price movements that come from speculative excesses.
- **The position limits.** These are the maximum number of contracts that one speculator can hold. The limits prevent speculators from having too much influence on the market. Bona fide hedgers are usually exempt.

**Key dates of a futures contract**

| Date                                   | Meaning                                                                                                                                  |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| First trading day                      | The first day when the market can trade the contract.                                                                                    |
| First position day (first intention day) | The first day when the short side can declare to the clearing house its intention to deliver.                                          |
| First notice day                       | The first day when the clearing house notifies a long side of a delivery. A long trader who does not want delivery usually closes the position before this day. |
| First delivery day                     | The first day when the delivery can occur.                                                                                               |
| Last trading day                       | The last day when the market can trade the contract. After this day, the open positions settle by delivery or by cash settlement.        |
| Last notice day                        | The last day when the clearing house can notify a long side of a delivery.                                                               |
| Last delivery day                      | The last day when the delivery can occur.                                                                                                |
| Final settlement date                  | For a cash-settled contract, the day when the exchange sets the final settlement price and closes the open positions.                    |

On CBOT Treasury and grain futures, the delivery always takes three business days. On the position day, the short side declares its intention to deliver, and the clearing house matches it with the oldest open long position. On the notice day, the two sides receive the match and the short side invoices the long side. On the delivery day, the short side delivers the asset and the long side pays. For this reason, the first position day, the first notice day and the first delivery day are usually three consecutive business days.

The exact dates, and the order of the last trading day and the last notice day, change from one contract to another. The contract specifications of the exchange give the real calendar of each contract.

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

A ban would make futures markets thin and costly and would hurt the hedgers it means to protect. The real concern is excessive or manipulative speculation, which exchanges and regulators control with the following rules (see [Forwards vs. futures](#forwards-vs-futures) for the margins and [Specification of a futures contract](#specification-of-a-futures-contract) for the limits).

- **Margin requirements** make each trader cover losses daily, so one default does not spread.
- **Daily price limits** cap how far the price can move in one session, which slows panic moves.
- **Position limits** cap the speculative contracts one trader can hold, which makes corners and squeezes harder.
- **Large-trader reporting** lets regulators watch big positions and act against manipulation.

Speculation is therefore a necessary part of a working futures market. It should be regulated, not banned.
