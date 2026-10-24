# Value Creation

Companies create value for their owners when they **invest cash today** to generate **more cash in the future**. The value that they create is the difference between the future cash inflows and the cost of the investments. This difference must be adjusted, because a cash flow of tomorrow is worth less than the same cash flow today. There are two reasons for this. The first is the **time value of money**, because the cash of today can earn a return in the meantime. The second is the **risk**, because the future cash flows are uncertain.

We can say that a company **creates value** when it generates cash flows for the capital that are higher than the cash flows of a financial asset with **equivalent risk**. The return of this asset is the return that we must **require** from the company. So the company creates value when its cash flows are **in excess of all its costs, including the cost of capital**.

This definition has three consequences.

- A company can be **profitable** and **destroy value**.
- A company that **grows** can **destroy value faster**.
- **Anything that does not increase the cash flows does not create value.** This is the principle of the **conservation of value**. An action that only changes who gets the cash flows, or how the accounts show them, does not change the value. 

## Definitions

### The Opportunity Cost of Capital

The investors who give their funds to a company give up the alternative, which is an investment in a financial asset with the same risk. The return of this alternative is the **opportunity cost of capital**, and it is the minimum return that the investors require from the company.

The opportunity cost of capital has two parts:

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

While earnings and cash flows are often correlated, earnings do not tell the whole story of value creation. Focusing too much on earnings leads companies to stray from a value-creating path.

### NOPAT

The **NOPAT** (*net operating profit after taxes*) represents the profit generated from the core operations of the company, after subtracting the income taxes related to those core operations.

$$NOPAT = EBIT (1 - \tau) = (EBITDA - D\&A)(1 - \tau)$$

- $\tau$ is the tax rate, so $\tau EBIT$ are the taxes on the operating profit.

### Invested Capital

The **IC** (*invested capital*) represents the cumulative amount that the business has invested in its core operations, primarily property, plant and equipment (PP&E) and working capital. These are the assets that generate the NOPAT, so the IC is the base for the return of the operations.

The **net investment** is the change in the invested capital in a period, i.e. the investment beyond the replacement of the depreciated assets.

$$\text{Net investment} = \Delta IC = IC_{t+1} - IC_t$$

### FCF

The **FCF** (*free cash flow*) is the cash flow generated by the core operations of the business after deducting the investments in new capital. It is the cash that is left over once the investments have been subtracted from the NOPAT. The FCF is before the interest, so it belongs to **all the providers of funds**, the creditors and the shareholders.

$$FCF = NOPAT - \text{Net investment}$$

### ROIC

The **return on invested capital** (ROIC) measures how much return the company earns on each monetary unit invested in its operations. A company creates value only if its ROIC is greater than its cost of capital.

$$ROIC = \frac{NOPAT}{IC}$$

The ROIC can be defined in two ways.

- **Average ROIC**, the return on all the capital, $\frac{NOPAT_t}{IC_t}$. It measures the result of all the past investments.
- **Incremental ROIC** (or *RONIC*, return on new invested capital), the return on the new capital, $\frac{NOPAT_{t+1} - NOPAT_t}{IC_{t+1} - IC_t} = \frac{\Delta NOPAT}{\text{Net investment}}$. It measures the result of the new investments, so it decides whether the growth creates value.

The two can be very different. A company with $IC = 500$ and $NOPAT = 100$ invests $100$ more, and its NOPAT increases to $108$. The average ROIC is $\frac{108}{600} = 18\%$, but the incremental ROIC is $\frac{8}{100} = 8\%$. With a WACC of $10\%$, the new investment destroys value, even if the average ROIC is higher than the WACC.

The ROIC is different from the **return on equity** (ROE), $ROE = \frac{\text{net income}}{\text{equity}}$. The ROE measures the return for the shareholders only, after the interest on the debt. The ROE changes with the debt of the company, so we compare it with the cost of equity $k_E$, not with the WACC.

### The Economic Profit

The **economic value added** (EVA), or **economic profit**, measures the value that the company creates in a period:

$$EVA = NOPAT - WACC \times IC = (ROIC - WACC) \times IC$$

The company creates value when $EVA > 0$, i.e. when $ROIC > WACC$.

Measuring value creation in terms of economic profit encourages a company to undertake investments that earn more than their cost of capital, even if their return is lower than the current average return.

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

The **IR** (*investment rate*, also called the *reinvestment rate*) is the portion of the NOPAT that the company invests back into the business.

$$IR = \frac{\text{Net investment}}{NOPAT}$$

### Growth

The **growth** ($g$) is the rate at which the NOPAT and the cash flows of the company grow each year.

$$g = \frac{NOPAT_{t+1} - NOPAT_t}{NOPAT_t}$$

## Relation between ROIC, Growth and Cash Flow

The value that a company creates is governed ultimately by its ROIC, its revenue growth and its ability to sustain both over time. Only if the ROIC exceeds the cost of capital will growth increase the value of the company. Growth at lower returns actually reduces the value of the company. For this reason, the near-term cash flow by itself may not be a meaningful performance indicator. A company that invests to grow at a high ROIC has a lower cash flow today, but it creates more value.

Growth, ROIC and cash flow are tied together mathematically in the following relationship.

$$g = ROIC \times IR$$

Another way to look at this relationship is in terms of cash flow.

$$FCF = NOPAT \times (1 - IR)$$

In this equation, the investment rate is equal to the growth divided by the ROIC.

$$FCF = NOPAT \times \left(1 - \frac{g}{ROIC}\right)$$

Here the ROIC is the return on the new capital (RONIC), because only the new investments make the NOPAT grow. If the new investments earn the same return as the existing capital, the two are equal.

Since the variables are tied together mathematically, you can describe the performance of a company with any two of them. We generally describe the performance of a company in terms of growth and ROIC, because you can analyze growth and ROIC across time and versus peers.

**Example**

A company has a revenue of $1{,}000$, a NOPAT of $100$ and an invested capital of $500$.

- $ROIC = \frac{100}{500} = 20\%$.
- The table shows the investment rate and the FCF for two growth rates.

| Growth $g$ | $IR = \frac{g}{ROIC}$ | $FCF = NOPAT (1 - IR)$ |
| --- | --- | --- |
| $0\%$ | $0\%$ | $100$ |
| $5\%$ | $25\%$ | $75$ |

With zero growth, the company does not need to invest, so its FCF is equal to its NOPAT. To grow at $5\%$, it must invest $25\%$ of its NOPAT, so its FCF today is lower. The growth creates value only because the ROIC of $20\%$ is higher than the cost of capital.

## Relation of Growth, ROIC and Value creation

For any level of growth, value increases with improvements in ROIC. *Ceteris paribus*, a higher ROIC is always good, because it means that the company does not have to invest as much to achieve a given level of growth. The same cannot be said of growth. When ROIC is high, faster growth increases value. But when ROIC is lower than the company's cost of capital, faster growth destroys value. When the return on capital is lower than the cost of capital, growing faster means investing more at value-destroying returns. Where ROIC equals the cost of capital, we can draw the dividing line between creating and destroying value through growth. On that line, value is neither created nor destroyed, regardless of how fast the company grows.

It is sometimes argued that even low-ROIC companies should strive for growth. The logic is that if a company grows, its ROIC will naturally increase. However, we find this true only for young, start-up businesses. Most often in mature companies, a low ROIC indicates a flawed business model or an unattractive industry structure. Do not fall for the trap that growth will lead to scale economies that automatically increase a company's return on capital. It almost never happens for mature businesses.

In general, companies already earning a high ROIC can generate more additional value by increasing their rate of growth, rather than their ROIC. For their part, low-ROIC companies will generate relatively  more value by focusing on increasing their ROIC.

Additionally, different types of growth earn different returns on capital, so not all growth is equally value-creating. Each company must understand the pecking order of growth-related value creation that applies to its industry and company type.

### A Profitable Company Can Destroy Value


The accounting profit (the net income) deducts the interest on the debt, but it does not deduct the cost of equity. A company can have a positive net income and a return that is lower than the return that its shareholders require.

**Example**

Use the company of [Financing Decisions](03-financing-decisions.md): equity of $600$, debt of $400$, $k_E = 12\%$, $k_D = 5\%$, $\tau = 25\%$ and $WACC = 8.7\%$. Assume that the book values are equal to the market values, and that the EBIT is $80$:

| Item | Value |
| --- | --- |
| EBIT | $80$ |
| − Interest ($5\% \times 400$) | $-20$ |
| = Profit before taxes | $60$ |
| − Taxes ($25\%$) | $-15$ |
| = **Net income** | $45$ |

The company is **profitable**: its net income is positive. But:

- $NOPAT = 80 \times (1 - 0.25) = 60$, so $ROIC = \frac{60}{1{,}000} = 6\%$, which is lower than the $WACC$ of $8.7\%$.
- $EVA = 60 - 8.7\% \times 1{,}000 = -27$: the company **destroys value**.
- From the point of view of the shareholders, the return on equity is $ROE = \frac{45}{600} = 7.5\%$, lower than the $12\%$ that they require.

The shareholders would earn more with an investment of the same risk in the financial markets.

### A Growing Company Can Destroy Value Faster

The growth needs investment. When the company reinvests a part of its $NOPAT$ at a return $ROIC$, the $NOPAT$ grows at the rate:

$$g = \text{reinvestment rate} \times ROIC \quad \Rightarrow \quad \text{reinvestment rate} = \frac{g}{ROIC}$$

The free cash flow is the part of the $NOPAT$ that the company does not reinvest, $FCF = NOPAT \left(1 - \frac{g}{ROIC}\right)$. With a constant growth, the value of the company is the value of a growing perpetuity:

$$V = \frac{NOPAT_1 \left(1 - \frac{g}{ROIC}\right)}{WACC - g}$$

- If $ROIC > WACC$, the value **increases** with the growth: each new investment creates value.
- If $ROIC = WACC$, the value is $\frac{NOPAT_1}{WACC}$ for each $g$: the growth is neutral.
- If $ROIC < WACC$, the value **decreases** with the growth: each new investment destroys value, so the faster the company grows, the faster it destroys value.

**Example**

A company has $NOPAT_1 = 100$ and $WACC = 10\%$:

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

Links last checked: 15 October 2026.

- Damodaran, Aswath. "Session 25: Valuation." Corporate Finance course, Spring 2024. NYU Stern School of Business. [Free online PDF](https://pages.stern.nyu.edu/~adamodar/podcasts/cfspr24/session25slides.pdf).
- Wikipedia. "Credit Spread (Bond)." [Online article](https://en.wikipedia.org/wiki/Credit_spread_(bond)).
- Wikipedia. "Earnings Before Interest, Taxes, Depreciation and Amortization." [Online article](https://en.wikipedia.org/wiki/Earnings_before_interest,_taxes,_depreciation_and_amortization).
- Wikipedia. "Economic Profit." [Online article](https://en.wikipedia.org/wiki/Economic_profit).
- Wikipedia. "Economic Value Added." [Online article](https://en.wikipedia.org/wiki/Economic_value_added).
- Wikipedia. "Risk Premium." [Online article](https://en.wikipedia.org/wiki/Risk_premium).
- Wikipedia. "Risk-Free Rate." [Online article](https://en.wikipedia.org/wiki/Risk-free_rate).
- Wikipedia. "Terminal Value (Finance)." [Online article](https://en.wikipedia.org/wiki/Terminal_value_(finance)).
