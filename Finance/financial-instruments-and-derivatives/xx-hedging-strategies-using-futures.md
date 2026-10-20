# Hedging Strategies Using Futures

Hedging using futures means taking a position in futures contracts to offset an exposure to the price of an asset. The goal of hedging is to reduce risk.

## Short/Long Hedges

If the exposure is such that the company gains when the price of the asset increases and loses when the price of the asset decreases, a **short hedge** is appropriate. An example is a producer who owns the asset or will sell it in the future.

If the exposure is the other way round, so that the company gains when the price of the asset decreases and loses when the price of the asset increases, a **long hedge** is appropriate. An example is a company that will need to buy the asset in the future.

As a rule of thumb, the futures position is the opposite of the exposure. A hedger who is effectively long the asset, such as a farmer who will sell wheat at harvest or a company that will receive foreign currency, goes short futures. A hedger who is effectively short the asset, such as an airline that will buy jet fuel or a company that has sold an asset it does not own yet, goes long futures. The gain on the futures position offsets the loss on the exposure when the price moves the wrong way. The hedge also gives up the gain when the price moves the right way, because its goal is to reduce risk, not to increase the expected profit.

A **perfect hedge** completely eliminates risk, because the gain or loss on the futures position exactly offsets the loss or gain on the exposure, so the outcome is fixed and known in advance. This requires the hedge to match the asset, the quantity, and the timing exactly. An **imperfect hedge** reduces risk but does not remove it, usually because of basis risk (see [Risks](#risks)), mismatched quantities, or timing differences. A perfect hedge gives certainty, not necessarily a better result. Because it removes the downside and the upside together, an imperfect hedge can turn out better when prices move in the hedger's favor, and worse when they move against it.

A perfect hedge does not lock in the current spot price $S_0$. It locks in the futures price $F_0$, which generally differs from $S_0$ because of the cost of carry.

$$
F_0 = S_0 e^{(c - y)T}
$$

Here $T$ is the time to maturity, $c = r + u - q$ is the cost of carry (the risk-free rate $r$, plus the storage cost $u$, minus the income yield $q$ of the asset), and $y$ is the convenience yield of holding a physical commodity. Interest and storage costs push the futures price above the spot price, while income from the asset and the convenience yield push it below. A perfect hedge therefore guarantees a known price for the future transaction, but that price is $F_0$, not $S_0$.

## Why hedge? Why not?

In a perfect market, hedging adds no value, because shareholders can hedge on their own. Real frictions, such as the costs of financial distress, change this.

**Reasons to hedge**

- **Focus on the core business.** Most companies have no skill in forecasting exchange rates, interest rates, or commodity prices. Hedging removes these risks and lets the company focus on what it does well.
- **Predictable cash flows.** A fixed price for a key input or a foreign currency payment makes budgets, pricing, and investment plans easier, and protects the cash needed for investment.
- **Lower risk of financial distress.** Hedging protects against the extreme price moves that could make the company unable to pay its debts. This reassures creditors, suppliers, and employees, and lets the company carry more debt.

**Reasons not to hedge**

- **Hedging is hard to explain.** If the hedge loses while the exposure gains, the net result is the same, but the board may see only the loss on the hedge and blame the treasurer.
- **Competitors do not hedge.** If no company in the industry hedges, prices tend to follow costs, so margins stay stable. A company that hedges alone breaks from this pattern and can end up with more risk, not less.
- **Shareholders can diversify.** Well-diversified shareholders may already offset the risk in their portfolios, so hedging adds cost without much benefit. The company, however, usually has better information on the risk and lower hedging costs than a single shareholder.

## Risks

**Basis risk**

The **basis** is the difference between the spot price of an asset and its futures price.

$$
\text{Basis} = \text{Spot price} - \text{Futures price}
$$

**Basis risk** is the risk that a hedge does not fully offset price changes, because the basis changes unpredictably over the life of the hedge. Futures prices converge to spot prices at delivery, but hedgers often close out their positions before that date, when the basis is uncertain. As a result, the gain or loss on the futures position does not exactly match the loss or gain on the asset. Basis risk also arises when the asset being hedged differs from the asset underlying the futures contract (see [Cross hedging](#cross-hedging)), or when the date of buying or selling the asset is uncertain.

**Strengthening and weakening of the basis**

The basis **strengthens** when it increases and **weakens** when it decreases. With a negative basis, which is common when the cost of carry is positive (see [Short/Long Hedges](#shortlong-hedges)), a move from −5 to −2 strengthens it and a move from −5 to −8 weakens it, so strengthening brings the two prices closer. With a positive basis, a move from +3 to +6 strengthens it and a move from +3 to +1 weakens it, so strengthening pushes the two prices apart. In both cases, the basis strengthens when the spot price gains relative to the futures price.

| Hedger       | Position                   | Gains when the basis | Loses when the basis |
| ------------ | -------------------------- | -------------------- | -------------------- |
| Short hedger | Long spot, short futures   | Strengthens          | Weakens              |
| Long hedger  | Short spot, long futures   | Weakens              | Strengthens          |

**Contango, backwardation, and the effective price**

The market is in **contango** when the futures price is above the spot price (negative basis), usually because of interest and storage costs. It is in **backwardation** when the futures price is below the spot price (positive basis), usually because of a high income or convenience yield (see the cost of carry in [Short/Long Hedges](#shortlong-hedges)). Some authors define both terms against the expected future spot price instead of the current spot price.

A hedge set up at time 1 and closed out at time 2 gives the following effective price, which is the selling price for a short hedger and the purchase price for a long hedger.

$$
\text{Effective price} = S_2 - (F_2 - F_1) = F_1 + b_2
$$

$F_1$ is known when the hedge starts, so the only uncertainty is the final basis $b_2$, which is the basis risk. If the hedge is closed out at maturity, $b_2 = 0$ and the effective price is $F_1$. A higher $b_2$ helps the short hedger and a lower $b_2$ helps the long hedger, as in the table above. For example, with $S_1 = 2.50$, $F_1 = 2.20$, $S_2 = 2.00$, and $F_2 = 1.90$, the basis weakens from 0.30 to 0.10 and the effective price is $2.20 + 0.10 = 2.30$.

Backwardation does not by itself favor a long hedger. The hedger locks in a price near $F_1$, which is below today's spot price $S_1$, but the alternative to the hedge is to buy at $S_2$, not at $S_1$. The result depends on how the basis changes, not on its sign at the start.
 
TODO add equations and formulas of minimum variance daily settlement vs not

## Cross hedging

The **optimal hedge ratio** (the minimum variance hedge ratio) is the slope of the best-fit line obtained when changes in the spot price are regressed against changes in the futures price.

## Stack and Roll

When no liquid futures contract matures later than the expiration of the hedge, a strategy known as **stack and roll** may be appropriate. It involves entering into a sequence of futures contracts.

1. When the first futures contract is near expiration, the hedger closes it out and enters into a second contract with a later delivery month.
2. When the second contract is near expiration, the hedger closes it out and enters into a third contract with a later delivery month.
3. The hedger continues in the same way until the end of the hedge.

The result is a long-dated futures contract created by trading a series of short-dated contracts.
