# Value Creation

Companies create value for their owners when they **invest cash today** to generate **more cash in the future**. The value that they create is the difference between the future cash inflows and the cost of the investments. This difference must be adjusted, because a cash flow of tomorrow is worth less than the same cash flow today. There are two reasons for this. The first is the **time value of money**, because the cash of today can earn a return in the meantime. The second is the **risk**, because the future cash flows are uncertain.

We can say that a company **creates value** when it generates cash flows for the capital that are higher than the cash flows of a financial asset with **equivalent risk**. The return of this asset is the return that we must **require** from the company. So the company creates value when its cash flows are **in excess of all its costs, including the cost of capital**.

This definition has two consequences.

- A company can be **profitable** and **destroy value**.
- A company that **grows** can **destroy value faster**.

The definition also gives the principle of the **conservation of value**. **Anything that does not increase the cash flows does not create value.** An action that only changes who gets the cash flows, or how the accounts show them, does not change the value. For example, without taxes, a company that borrows to pay its shareholders does not change its value, because its cash flow stays the same (see [Financing Decisions](03-financing-decisions.md)).

## Definitions

### Opportunity Cost of Capital

The investors who give their funds to a company give up the alternative, which is an investment in a financial asset with the same risk. The return of this alternative is the **opportunity cost of capital**, and it is the minimum return that the investors require from the company.

The opportunity cost of capital has two parts.

$$\text{opportunity cost of capital} = r_f + \text{risk premium}$$

- $r_f$ is the **risk-free rate**, the return of an asset with no risk (e.g. a government bond). It pays for the **time value of money**.
- The **risk premium** is the extra return that the investors require because they take **risk**. It is called a premium because it is a payment for the risk, like the premium of an insurance contract.

**The Cost of Capital and the WACC**

The **cost of capital** of a company is the opportunity cost of capital, seen from the company. The company must offer at least the return of the alternative, or the investors do not give it their funds. Each provider of funds has its own opportunity cost, $k_E$ for the shareholders and $k_D$ for the creditors. The **weighted average cost of capital** (WACC) combines them (see [Financing Decisions](03-financing-decisions.md)).

The WACC is the opportunity cost of all the capital of the company, with two differences.

- **Taxes.** The interest is deductible from the taxable profit, so the cost of debt for the company is $k_D (1-\tau)$. This is lower than the $k_D$ that the creditors require.
- **Risk.** The WACC is the opportunity cost for the average risk of the company. A project with a different risk needs its own rate (see [Investment Decisions](02-investment-decisions.md)).

### Revenue

The **revenue** is the total amount that the company earns from the sale of its products and services in a period, before it deducts any cost. It is the first line of the table in [Operating Decisions](01-operating-decisions.md).

$$\text{Revenue} = p_t q_t$$

- $p_t$ is the unit price of the products sold in period $t$.
- $q_t$ is the quantity sold.

The revenue is recorded when the company sells, not when the customers pay. The difference between the two is in the receivables, which are a part of the working capital. So the revenue is not the cash that comes in during the period.

The revenue shows the size of the business, but it does not show how much of it the company keeps. A company can increase its revenue with lower prices and earn less.

### EBITDA

The **EBITDA** (*earnings before interest, taxes, depreciation and amortization*) is the operating result of the company before the depreciation and the amortization. It is the first profit in the table of [Operating Decisions](01-operating-decisions.md), after the variable and the fixed cash costs.

$$EBITDA = (p_t - v_t) q_t - F_t = EBIT + D\&A$$

- $v_t$ is the unit variable cost, e.g. the raw materials of each unit. So $p_t - v_t$ is the unit contribution margin.
- $F_t$ are the fixed cash costs, which do not depend on the quantity sold (e.g. rent, salaries). They do not include the depreciation and the amortization.
- $D\&A$ is the depreciation and the amortization, so $EBIT$ is the operating profit after them.

The EBITDA is **not** a cash flow, and it does not measure the value created. It ignores the taxes, the investment in fixed capital (CapEx) and the investment in working capital. It also ignores the cost of capital. A capital-intensive company can have a high EBITDA and a low free cash flow.

### NOPAT

The **NOPAT** (*net operating profit after taxes*) is the profit of the core operations of the company, after the taxes on this profit. The taxes are calculated on the EBIT, as if the company had no debt, so the NOPAT does not depend on the financing of the company.

$$NOPAT = EBIT (1 - \tau) = (EBITDA - D\&A)(1 - \tau)$$

- $\tau$ is the tax rate, so $\tau EBIT$ are the taxes on the operating profit.

### Invested Capital

The **IC** (*invested capital*) is the total amount that the company has invested in its core operations up to a given date. It is mainly the property, plant and equipment (PP&E) and the working capital. These are the assets that generate the NOPAT, so the IC is the base for the return of the operations.

The **net investment** is the change in the invested capital in a period, i.e. the investment beyond the replacement of the depreciated assets.

$$\text{Net investment} = \Delta IC = IC_{t+1} - IC_t$$

### FCF

The **FCF** (*free cash flow*) is the cash flow of the core operations after the investments in new capital. It is the part of the NOPAT that remains after the net investment. The FCF is before the interest, so it belongs to **all the providers of funds**, the creditors and the shareholders.

$$FCF = NOPAT - \text{Net investment}$$

### ROIC

The **return on invested capital** (ROIC) is the return that the company earns on each unit of capital that it invests in its operations. A company creates value only if its ROIC is higher than its cost of capital.

$$ROIC = \frac{NOPAT}{IC}$$

The ROIC can be defined in two ways.

- **Average ROIC**, the return on all the capital, $\frac{NOPAT_t}{IC_t}$. It measures the result of all the past investments.
- **Incremental ROIC** (or *RONIC*, return on new invested capital), the return on the new capital, $\frac{NOPAT_{t+1} - NOPAT_t}{IC_{t+1} - IC_t} = \frac{\Delta NOPAT}{\text{Net investment}}$. It measures the result of the new investments, so it decides whether the growth creates value.

The two can be very different. A company with $IC = 500$ and $NOPAT = 100$ invests $100$ more, and its NOPAT increases to $108$. The average ROIC is $\frac{108}{600} = 18\%$, but the incremental ROIC is $\frac{8}{100} = 8\%$. With a WACC of $10\%$, the new investment destroys value, even though the average ROIC is higher than the WACC.

The ROIC is different from the **return on equity** (ROE), $ROE = \frac{\text{net income}}{\text{equity}}$. The ROE measures the return for the shareholders only, after the interest on the debt. The ROE changes with the debt of the company, so we compare it with the cost of equity $k_E$, not with the WACC.

### EVA

The **economic value added** (EVA), or **economic profit**, measures the value that the company creates in a period.

$$EVA = NOPAT - WACC \times IC = (ROIC - WACC) \times IC$$

The company creates value when $EVA > 0$, i.e. when $ROIC > WACC$.

A target on the EVA makes a company accept each investment that earns more than the WACC, even if the return of the investment is lower than the current average ROIC.

**Example**

A company has $IC = 1{,}000$, a ROIC of $20\%$ and a WACC of $10\%$. It can invest $500$ more in a project that earns $15\%$.

| Item | Without the project | With the project |
| --- | --- | --- |
| IC | $1{,}000$ | $1{,}500$ |
| NOPAT | $200$ | $200 + 75 = 275$ |
| ROIC | $20.0\%$ | $18.3\%$ |
| EVA ($NOPAT - 10\% \times IC$) | $100$ | $125$ |

The project reduces the average ROIC, but it increases the EVA by $25$, because its return of $15\%$ is higher than the WACC. A target on the ROIC would reject the project, and a target on the EVA would accept it.

### Investment Rate

The **IR** (*investment rate*, also called the *reinvestment rate*) is the part of the NOPAT that the company reinvests in the business.

$$IR = \frac{\text{Net investment}}{NOPAT}$$

### Growth

The **growth** ($g$) is the rate at which the NOPAT grows each year. If the investment rate is constant, the FCF grows at the same rate.

$$g = \frac{NOPAT_{t+1} - NOPAT_t}{NOPAT_t}$$

## A Profitable Company Can Destroy Value

The accounting profit (the net income) deducts the interest on the debt, but it does not deduct the cost of equity. A company can have a positive net income and a return that is lower than the return that its shareholders require.

**Example**

Consider a company with equity of $600$, debt of $400$, $k_E = 12\%$, $k_D = 5\%$, $\tau = 25\%$ and $WACC = 8.7\%$. Assume that the book values are equal to the market values, so the invested capital is $1{,}000$, and that the EBIT is $80$.

| Item | Value |
| --- | --- |
| EBIT | $80$ |
| − Interest ($5\% \times 400$) | $-20$ |
| = Profit before taxes | $60$ |
| − Taxes ($25\%$) | $-15$ |
| = **Net income** | $45$ |

The company is **profitable**, because its net income is positive. But it **destroys value**.

- $NOPAT = 80 \times (1 - 0.25) = 60$, so $ROIC = \frac{60}{1{,}000} = 6\%$, which is lower than the $WACC$ of $8.7\%$.
- $EVA = 60 - 8.7\% \times 1{,}000 = -27$, so the company destroys $27$ of value in the year.
- From the point of view of the shareholders, the return on equity is $ROE = \frac{45}{600} = 7.5\%$, lower than the $12\%$ that they require.

The shareholders would earn more with an investment of the same risk in the financial markets.

The accounting profit and the cash flows often move together, but the accounting profit does not show all of the value creation. A company that looks only at its accounting profit can take decisions that destroy value (see the example of an R&D cut in [Why Value Value?](05-why-value-value.md)).

## Relation between Growth, ROIC and Cash Flow

The value that a company creates depends on its ROIC, its growth and how long it can keep them. The cash flow of one year alone is not a good measure of the performance. A company that invests to grow has a lower cash flow today, but it creates more value if its ROIC is higher than the WACC.

The growth, the ROIC and the investment rate are linked. Each unit of net investment adds the ROIC to the NOPAT of the next year, so $\Delta NOPAT = ROIC \times \text{Net investment}$. Divide both sides by the NOPAT to get the growth.

$$g = ROIC \times IR$$

The same relation gives the cash flow, because the FCF is the part of the NOPAT that the company does not reinvest.

$$FCF = NOPAT \times (1 - IR)$$

From the first formula, the investment rate is equal to the growth divided by the ROIC.

$$FCF = NOPAT \times \left(1 - \frac{g}{ROIC}\right)$$

Here the ROIC is the return on the new capital (RONIC), because only the new investments make the NOPAT grow. If the new investments earn the same return as the existing capital, the two are equal.

The three variables are linked, so any two of them describe the performance of a company. The usual choice is the growth and the ROIC, because they are easy to compare over time and with similar companies.

**Example**

A company expects a NOPAT of $100$ next year, with an invested capital of $500$, so its ROIC is $\frac{100}{500} = 20\%$. The new investments earn the same ROIC, and the WACC is $10\%$. The table shows the investment rate and the FCF for two growth rates.

| Growth $g$ | $IR = \frac{g}{ROIC}$ | $FCF = NOPAT (1 - IR)$ |
| --- | --- | --- |
| $0\%$ | $0\%$ | $100$ |
| $5\%$ | $25\%$ | $75$ |

With zero growth, the company does not need to invest, so its FCF is equal to its NOPAT. To grow at $5\%$, it must invest $25\%$ of its NOPAT, so its FCF is lower. But the growth creates value, because the ROIC of $20\%$ is higher than the WACC of $10\%$. With the formula in the last section, the value of the company increases from $1{,}000$ to $\frac{75}{10\% - 5\%} = 1{,}500$.

## Relation between Growth, ROIC and Value

For the same NOPAT and any positive growth, the value increases with the ROIC, because the company must invest less to get the same growth. With zero growth, the company does not invest, so the ROIC does not change the value.

The effect of the growth depends on the ROIC. A faster growth increases the value only if the ROIC is higher than the WACC. If the ROIC is lower than the WACC, a faster growth means more investment at a return below the cost of capital, so it decreases the value. If the ROIC is equal to the WACC, the growth does not change the value. The last section shows these three cases with a formula and a table.

Some argue that a company with a low ROIC should grow, because its ROIC increases with its size. In practice, this is true only for young companies. In a mature company, a low ROIC usually comes from a weak business model or an unattractive industry. The growth rarely gives economies of scale that are large enough to correct it.

In general, a company with a high ROIC creates more value if it grows faster than if it increases its ROIC further. A company with a low ROIC creates more value if it first increases its ROIC.

The types of growth earn different returns, so they do not all create the same value. The growth from new products or new markets usually creates the most value. The growth from a larger share of a mature market usually creates less, because the competitors react, for example with lower prices. The growth from acquisitions often creates little value for the buyer, because the buyer usually pays a premium over the value of the target.

## A Growing Company Can Destroy Value Faster

The free cash flow is the part of the $NOPAT$ that the company does not reinvest, $FCF = NOPAT \left(1 - \frac{g}{ROIC}\right)$. If the growth is constant and lower than the WACC, the value of the company is the value of a growing perpetuity. As in the formula of the FCF, the ROIC is the return on the new capital, and it must be constant.

$$V = \frac{NOPAT_1 \left(1 - \frac{g}{ROIC}\right)}{WACC - g}$$

- If $ROIC > WACC$, the value **increases** with the growth, because each new investment creates value.
- If $ROIC = WACC$, the value is $\frac{NOPAT_1}{WACC}$ for each $g$, so the growth has no effect.
- If $ROIC < WACC$, the value **decreases** with the growth, because each new investment destroys value. So the faster the company grows, the faster it destroys value.

**Example**

A company has $NOPAT_1 = 100$ and $WACC = 10\%$. The table shows its value $V$ for three ROICs and four growth rates.

| Growth $g$ | $ROIC = 8\%$ | $ROIC = 10\%$ | $ROIC = 15\%$ |
| --- | --- | --- | --- |
| $0\%$ | $1{,}000$ | $1{,}000$ | $1{,}000$ |
| $2\%$ | $937.5$ | $1{,}000$ | $1{,}083.3$ |
| $4\%$ | $833.3$ | $1{,}000$ | $1{,}222.2$ |
| $6\%$ | $625.0$ | $1{,}000$ | $1{,}500.0$ |

For example, with $ROIC = 8\%$ and $g = 4\%$, the company reinvests $\frac{4\%}{8\%} = 50\%$ of its $NOPAT$, so $FCF = 50$ and $V = \frac{50}{10\% - 4\%} = 833.3$.

![](Attachments/growth-and-value.svg)

Growth is not a goal in itself. The company must first earn a return above its cost of capital, and only then grow. The note [Why Value Value?](05-why-value-value.md) compares the long-term value with the other possible goals of a company (the share price today, the accounting profit and the growth).

## References

Links last checked: 24 October 2026.

- Damodaran, Aswath. "Session 25: Valuation." Corporate Finance course, Spring 2024. NYU Stern School of Business. [Free online PDF](https://pages.stern.nyu.edu/~adamodar/podcasts/cfspr24/session25slides.pdf).
- Koller, Tim, Marc Goedhart, and David Wessels. 2025. *Valuation: Measuring and Managing the Value of Companies*. 8th ed. McKinsey & Company. Hoboken, NJ: Wiley. Chapter 3, "Fundamental Principles of Value Creation."
- Koller, Tim, Marc Goedhart, and David Wessels. 2025. *Valuation: Measuring and Managing the Value of Companies*. 8th ed. McKinsey & Company. Hoboken, NJ: Wiley. Chapter 9, "Growth."
- Wikipedia. "Contribution Margin." [Online article](https://en.wikipedia.org/wiki/Contribution_margin).
- Wikipedia. "Cost of Capital." [Online article](https://en.wikipedia.org/wiki/Cost_of_capital).
- Wikipedia. "Earnings Before Interest, Taxes, Depreciation and Amortization." [Online article](https://en.wikipedia.org/wiki/Earnings_before_interest,_taxes,_depreciation_and_amortization).
- Wikipedia. "Economic Value Added." [Online article](https://en.wikipedia.org/wiki/Economic_value_added).
- Wikipedia. "Economies of Scale." [Online article](https://en.wikipedia.org/wiki/Economies_of_scale).
- Wikipedia. "Free Cash Flow." [Online article](https://en.wikipedia.org/wiki/Free_cash_flow).
- Wikipedia. "Modigliani–Miller Theorem." [Online article](https://en.wikipedia.org/wiki/Modigliani%E2%80%93Miller_theorem).
- Wikipedia. "Net Operating Profit After Taxes." [Online article](https://en.wikipedia.org/wiki/Net_operating_profit_after_taxes).
- Wikipedia. "Opportunity Cost." [Online article](https://en.wikipedia.org/wiki/Opportunity_cost).
- Wikipedia. "Perpetuity." [Online article](https://en.wikipedia.org/wiki/Perpetuity).
- Wikipedia. "Profit (Economics)." [Online article](https://en.wikipedia.org/wiki/Profit_(economics)).
- Wikipedia. "Return on Capital." [Online article](https://en.wikipedia.org/wiki/Return_on_capital).
- Wikipedia. "Return on Equity." [Online article](https://en.wikipedia.org/wiki/Return_on_equity).
- Wikipedia. "Revenue." [Online article](https://en.wikipedia.org/wiki/Revenue).
- Wikipedia. "Revenue Recognition." [Online article](https://en.wikipedia.org/wiki/Revenue_recognition).
- Wikipedia. "Risk Premium." [Online article](https://en.wikipedia.org/wiki/Risk_premium).
- Wikipedia. "Risk-Free Rate." [Online article](https://en.wikipedia.org/wiki/Risk-free_rate).
- Wikipedia. "Tax Shield." [Online article](https://en.wikipedia.org/wiki/Tax_shield).
- Wikipedia. "Terminal Value (Finance)." [Online article](https://en.wikipedia.org/wiki/Terminal_value_(finance)).
- Wikipedia. "Time Value of Money." [Online article](https://en.wikipedia.org/wiki/Time_value_of_money).
- Wikipedia. "Weighted Average Cost of Capital." [Online article](https://en.wikipedia.org/wiki/Weighted_average_cost_of_capital).
- Wikipedia. "Working Capital." [Online article](https://en.wikipedia.org/wiki/Working_capital).
