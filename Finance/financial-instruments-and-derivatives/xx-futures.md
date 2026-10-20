# Futures

## Long vs. short forwards

A forward is an agreement made today to trade an asset on a future date at a fixed delivery price $K$. The long party agrees to buy the asset, and the short party agrees to sell it. Nothing changes hands at the start. The contract is set up to be worth zero to both sides, and the trade happens at maturity.

The terms "long" and "short" describe your side of the contract and which way you benefit from price moves. Long means you'll own the asset, so you gain if the price rises. Short means you'll deliver it, so you gain if the price falls. The difference is defined by the obligation to buy or sell, not by expectations.

At maturity, with $S_T$ as the spot price, the payoffs of the two sides are the following.

$$\text{Long payoff} = S_T - K$$

$$\text{Short payoff} = K - S_T$$

Since there's no upfront cost, payoff equals profit. Both sides are obligated, so the payoffs are straight lines, with unlimited gains and losses for both.

**Extending to options**

With options, "long" means you bought the option (the holder) and "short" means you sold or wrote it (the writer). The holder has a right, the writer has an obligation, and the holder pays a premium upfront ($c$ for a call, $p$ for a put).

| Position   | Right or obligation             | Profit                 | Gains if               |
| ---------- | ------------------------------- | ---------------------- | ---------------------- |
| Long call  | Right to buy                    | $\max(S_T - K, 0) - c$ | The price rises        |
| Short call | Obligation to sell if exercised | $c - \max(S_T - K, 0)$ | The price doesn't rise |
| Long put   | Right to sell                   | $\max(K - S_T, 0) - p$ | The price falls        |
| Short put  | Obligation to buy if exercised  | $p - \max(K - S_T, 0)$ | The price doesn't fall |

The key difference from forwards is that with options, "long" doesn't always mean buying the asset. A long put gives you the right to sell. Because the holder only exercises when it's profitable, option payoffs are kinked rather than straight. The holder's maximum loss is the premium, while the writer's maximum gain is that premium, with potentially large losses (unlimited for a short call).

**The zero-sum link**

In both forwards and options, the long's profit plus the short's profit always equals zero, so one side's gain is exactly the other's loss. The premium is the price the option holder pays to replace a forward's obligation with a right. That changes how risk is divided between the two sides, but not the zero-sum total.

## Forwards vs. futures

A **futures contract** is also an agreement to buy or sell an asset on a future date at a price fixed today. The economic idea is the same as a forward, but the two contracts trade in different ways. A forward is a private contract between two parties in the OTC market. A futures contract trades on an exchange, with the standardized terms, the clearing house and the margin of an exchange-traded market (see the section on exchange-traded and OTC markets in [Markets and Types of Traders](xx-markets-and-type-of-traders.md)).

|                  | Forward                                      | Futures                                           |
| ---------------- | -------------------------------------------- | ------------------------------------------------- |
| Market           | OTC, private between two parties             | Exchange                                          |
| Terms            | Customized                                   | Standardized by the exchange                      |
| Settlement       | One settlement at maturity                   | Daily settlement (marking to market)              |
| Credit risk      | Each side depends on the other side          | Greatly reduced by the clearing house and margin  |
| Delivery date    | Usually one specified date                   | Often a range of dates, chosen by the short side  |
| End of contract  | Usually held to delivery or cash settlement  | Usually closed out before maturity                |

**Daily settlement**

The main practical difference is the timing of the gains and losses. With a forward, the whole gain or loss arrives at maturity. With a futures contract, the gain or loss from the change of the futures price goes into or out of the margin account of the trader at the end of each day. This process is **marking to market**. If the balance falls below the maintenance margin, the trader receives a margin call and must add funds to bring the balance back to the initial margin, or the broker closes the position.

The initial margin is a performance bond, usually a small percentage of the value of the contract. It is not a loan and not a price paid for the contract, so a futures contract is also worth zero to both sides at the start, the same as a forward. The margin makes sure that the losers can pay the winners, stops the losses from building up over time, and protects the broker and the clearing house from traders who cannot pay. Because the margin is only a small part of the value of the contract, it also gives leverage, which magnifies both gains and losses.

**Example**

A trader goes long one futures contract at a price of 100 and holds it to maturity, where the futures price is equal to the spot price $S_T = 102$.

| Day          | Futures price | Daily gain or loss | Cumulative gain or loss |
| ------------ | ------------- | ------------------ | ----------------------- |
| 0            | 100           | -                  | -                       |
| 1            | 101           | +1                 | +1                      |
| 2            | 99            | -2                 | -1                      |
| 3 (maturity) | 102           | +3                 | +2                      |

The total gain is 2, which is the final price minus the initial price. A long forward with $K = 100$ gives the same payoff, $S_T - K = 102 - 100 = 2$, if we ignore the interest on the margin balance. The total is the same, but the futures contract pays it day by day and the forward pays it once at maturity.

**Forward and futures prices**

If the interest rates are constant, the forward price and the futures price for the same maturity are equal. If the interest rates change in a random way, the two prices can differ, because the trader reinvests the daily gains and finances the daily losses at the rates of each day. The difference depends on the correlation between the interest rates and the price of the asset. If the price of the asset tends to rise when the interest rates rise, the long side of a futures contract reinvests its gains at higher rates, so the futures price is higher than the forward price. For short maturities the difference is usually small.

## Specification of a futures contract

When an exchange creates a new futures contract, it must specify the exact terms of the agreement between the two sides. These standard terms are what make futures contracts interchangeable. The goal of the design is a contract that attracts enough hedgers and speculators to give good liquidity. The main parameters are the following.

- **The asset.** The exchange specifies the underlying asset and, for a commodity, the grades or qualities that the short side can deliver. If the short side delivers a grade other than the standard one, the price receives an adjustment, a premium or a discount.
- **The contract size.** This is the quantity of the asset in one contract. A contract that is too large excludes the small investors and hedgers. A contract that is too small has high trading costs, because each contract has a cost to trade.
- **The delivery arrangements.** The exchange specifies the place of delivery. The place is important when the transport costs are significant, and the price can receive an adjustment for a place other than the standard one.
- **The delivery months.** The exchange specifies the months of the contract and the period in each month when the delivery can occur. Many financial futures use the quarterly cycle of March, June, September and December.
- **The price quotes.** The exchange specifies how it quotes the price and the tick size, which is the minimum movement of the price.
- **The daily price limits.** These are the maximum movements of the price in one day. A movement equal to the limit is a limit move (limit up or limit down). The limits prevent large price movements that come from speculative excesses.
- **The position limits.** These are the maximum number of contracts that one speculator can hold. The limits prevent speculators from having too much influence on the market. Bona fide hedgers are usually exempt.

The first four parameters (asset, contract size, delivery arrangements and delivery months) are the most important in the design of a new contract.

**Key dates of a futures contract**

| Date                                   | Meaning                                                                                                                                  |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| First trading day                      | The first day when the market can trade the contract.                                                                                    |
| First position day (first intention day) | The first day when the short side can declare to the clearing house its intention to deliver.                                          |
| First notice day                       | The first day when the clearing house matches a short side with a long side and notifies the two sides. A long trader who does not want delivery usually closes the position before this day. |
| First delivery day                     | The first day when the delivery can occur.                                                                                               |
| Last trading day                       | The last day when the market can trade the contract. After this day, the open positions settle by delivery or by cash settlement.        |
| Last notice day                        | The last day when the clearing house can notify a long side of a delivery.                                                               |
| Last delivery day                      | The last day when the delivery can occur.                                                                                                |
| Final settlement date                  | For a cash-settled contract, the day when the exchange sets the final settlement price and closes the open positions.                    |

The delivery takes three business days. On the position day, the short side declares its intention to deliver. On the notice day, the clearing house matches the short side with a long side, usually the oldest open long position, and notifies the two sides. On the delivery day, the short side delivers the asset and the long side pays. For this reason, the first position day, the first notice day and the first delivery day are usually three consecutive business days.

The exact dates, and the order of the last trading day and the last notice day, change from one contract to another. The contract specifications of the exchange give the real calendar of each contract.
