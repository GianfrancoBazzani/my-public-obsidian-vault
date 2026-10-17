# Operating Decisions

## Definition

**Operating decisions** are the decisions related to the **maximization** and the **quality** of the generation of **cash flows** of a company, under given conditions. Examples: marketing, pricing strategy, cost management, collection and payment terms (with customers and suppliers), etc.

They are related to the **management** of the business, its **efficiency** and its **robustness** in the short to medium term.

They are the decisions involved in going **from revenue to free cash flow (FCF)**. The FCF is the **profit** available after all the costs except the **cost of capital**.

"Under given conditions" means that the operating decisions take the capital of the company and its funding as given. They choose how to use the capital that the investment and financing decisions provide. In the optimization problem of [Companies and Corporate Finance](00-companies-and-corporate-finance.md) (section "Value creation as an optimization problem"), the operating decisions are the prices $p_t$ and the quantities $q_t$, together with the management of the costs $v_t$, $F_t$ and of the working capital $\Delta K_t^W$.

## From revenue to free cash flow

The table shows the steps from the revenue to the FCF, and the operating decisions that act on each step. The notation is the same as in [Companies and Corporate Finance](00-companies-and-corporate-finance.md), with $\tau$ for the tax rate.

| Step | Formula | Operating decisions |
| --- | --- | --- |
| Revenue | $p_t q_t$ | Marketing, pricing strategy |
| − Variable costs | $v_t q_t$ | Cost management, purchasing |
| = Contribution margin | $(p_t - v_t) q_t$ | |
| − Fixed cash costs | $F_t$ | Cost management |
| = EBITDA (operating result) | $(p_t - v_t) q_t - F_t$ | |
| − Depreciation and amortization | $D\&A$ | |
| = EBIT (operating profit) | $EBIT$ | |
| − Taxes on the operating profit | $\tau EBIT$ | |
| = NOPAT (operating profit after taxes) | $EBIT (1-\tau)$ | |
| + Depreciation and amortization | $D\&A$ | |
| − Change in working capital | $\Delta K_t^W$ | Collection and payment terms, inventory |
| − Capital expenditure | $I_t$ | (investment decision) |
| = Free cash flow | $\Pi_t$ | |

In one formula:

$$FCF = EBIT (1-\tau) + D\&A - \Delta K_t^W - I_t$$

- The depreciation and amortization are deducted to calculate the taxes, because they reduce the taxable profit. They are then added back, because they are not a payment of cash.
- The change in the working capital and the capital expenditure are payments of cash that do not appear as costs in the profit, so they are deducted.

> [!NOTE]
> The capital expenditure $I_t$ is an investment decision, not an operating decision. The operating decisions act on all the other steps of the table. The FCF also deducts $I_t$, because the cash that goes into new fixed capital is not available to the providers of funds.

## Free cash flow and the cost of capital

The FCF is the cash available to **all the providers of funds**, the creditors and the shareholders. For this reason it does not deduct the payments to them (interest, debt repayments and dividends). These payments are the cost of capital. The cost of capital does not appear in the FCF. It appears in the discount rate (the WACC), which converts the future FCF into the value of the company.

> [!NOTE]
> The slide calls the FCF a "profit", but the FCF is a cash measure, not an accounting profit. It is different from the net income for two reasons. It deducts the purchase of fixed capital and the changes in working capital. It does not deduct the costs that are not payments of cash, such as the depreciation.

The taxes in the table are calculated on the EBIT, as if the company had no debt. In reality the interest is deductible from the taxable profit, so debt reduces the taxes (the **interest tax shield**). This benefit is not in the FCF. It is in the WACC, which uses the cost of debt after taxes, $\kappa_D (1-\tau)$.

## Quality of the cash flows

The operating decisions must maximize the cash flows, but also their **quality**. The cash flows have a high quality when they are:

- **Recurrent:** they come from the regular activity of the company, not from one-time events (e.g. the sale of an asset).
- **Predictable:** they are stable and easy to forecast, so the risk of the company is lower.
- **Backed by cash:** the profit becomes cash. A profit that stays in receivables or inventories is not available to the providers of funds.

In accounting, the similar concept of **earnings quality** measures how well the reported profit predicts the future cash flows, i.e. how "repeatable, controllable and bankable" the profit is.

## Efficiency: working capital and the cash conversion cycle

The collection and payment terms and the management of the inventories set the **working capital** $K^W$. The **cash conversion cycle** (CCC) measures the number of days between the payment of cash to the suppliers and the collection of cash from the customers:

$$CCC = DIO + DSO - DPO$$

- $DIO$ (days inventory outstanding, or inventory conversion period) is the average number of days that the products stay in inventory: $DIO = \frac{\text{Average inventory}}{\text{Cost of goods sold} / 365}$.
- $DSO$ (days sales outstanding, or receivables collection period) is the average number of days that the customers take to pay: $DSO = \frac{\text{Average accounts receivable}}{\text{Sales} / 365}$.
- $DPO$ (days payable outstanding, or payables deferral period) is the average number of days that the company takes to pay its suppliers: $DPO = \frac{\text{Average accounts payable}}{\text{Purchases} / 365}$.

A shorter cycle needs less working capital. A decrease in the working capital ($\Delta K_t^W < 0$) increases the FCF. The company can shorten the cycle in three ways:

- Collect from the customers sooner (lower $DSO$), e.g. with stricter credit terms. Credit terms that are too strict can cause a loss of sales.
- Keep less inventory (lower $DIO$). Too little inventory can cause a loss of sales when the products are not available.
- Pay the suppliers later (higher $DPO$). Late payment beyond the agreed terms can damage the relations with the suppliers and the credit rating of the company.

## Robustness: operating leverage and the break-even point

The robustness of the business depends on the structure of its costs. The **operating leverage** measures how much the operating result changes when the sales change. The **degree of operating leverage** (DOL) is:

$$DOL = \frac{\%\ \text{change in the operating result}}{\%\ \text{change in the sales}} = \frac{(p_t - v_t) q_t}{(p_t - v_t) q_t - F_t}$$

- The numerator is the contribution margin, and the denominator is the operating result.
- If the company has no fixed costs ($F_t = 0$), the DOL is $1$: the operating result changes by the same percentage as the sales.
- The higher the fixed costs, the higher the DOL. The operating result increases faster when the sales increase, and decreases faster when the sales decrease. A high DOL makes the company less robust to a fall in the sales.

The **break-even point** is the quantity $q^*$ at which the operating result is zero, i.e. the contribution margin covers exactly the fixed costs:

$$(p_t - v_t) q^* - F_t = 0 \quad \Rightarrow \quad q^* = \frac{F_t}{p_t - v_t}$$

Below $q^*$ the company has an operating loss. The DOL is highest near the break-even point, where a small change in the sales causes a large percentage change in the operating result.

**Example**

A company sells $q = 1{,}000{,}000$ units at a price $p = 50$, with a unit variable cost $v = 10$ and fixed costs $F = 10{,}000{,}000$:

- Contribution margin: $(50 - 10) \times 1{,}000{,}000 = 40{,}000{,}000$.
- Operating result: $40{,}000{,}000 - 10{,}000{,}000 = 30{,}000{,}000$.
- DOL: $\frac{40{,}000{,}000}{30{,}000{,}000} \approx 1.33$. An increase of 10% in the sales causes an increase of about 13.3% in the operating result.
- Break-even point: $q^* = \frac{10{,}000{,}000}{50 - 10} = 250{,}000$ units.

## References

Links last checked: 15 October 2026.

- Dahlquist, Julie, and Rainford Knight. 2022. *Principles of Finance*. OpenStax. Section 5.6, "Operating Cash Flow and Free Cash Flow to the Firm (FCFF)." [Free online edition](https://openstax.org/books/principles-finance/pages/5-6-operating-cash-flow-and-free-cash-flow-to-the-firm-fcff).
- Dahlquist, Julie, and Rainford Knight. 2022. *Principles of Finance*. OpenStax. Section 17.3, "Calculating the Weighted Average Cost of Capital." [Free online edition](https://openstax.org/books/principles-finance/pages/17-3-calculating-the-weighted-average-cost-of-capital).
- Dahlquist, Julie, and Rainford Knight. 2022. *Principles of Finance*. OpenStax. Section 19.1, "What Is Working Capital?" [Free online edition](https://openstax.org/books/principles-finance/pages/19-1-what-is-working-capital).
- Dahlquist, Julie, and Rainford Knight. 2022. *Principles of Finance*. OpenStax. Section 19.4, "Receivables Management." [Free online edition](https://openstax.org/books/principles-finance/pages/19-4-receivables-management).
- Wikipedia. "Break-Even Point." [Online article](https://en.wikipedia.org/wiki/Break-even_point).
- Wikipedia. "Cash Conversion Cycle." [Online article](https://en.wikipedia.org/wiki/Cash_conversion_cycle).
- Wikipedia. "Contribution Margin." [Online article](https://en.wikipedia.org/wiki/Contribution_margin).
- Wikipedia. "Earnings Quality." [Online article](https://en.wikipedia.org/wiki/Earnings_quality).
- Wikipedia. "Free Cash Flow." [Online article](https://en.wikipedia.org/wiki/Free_cash_flow).
- Wikipedia. "Operating Leverage." [Online article](https://en.wikipedia.org/wiki/Operating_leverage).
- Wikipedia. "Weighted Average Cost of Capital." [Online article](https://en.wikipedia.org/wiki/Weighted_average_cost_of_capital).
