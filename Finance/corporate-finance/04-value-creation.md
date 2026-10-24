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

## The Economic Profit

The **economic value added** (EVA), or **economic profit**, measures the value that the company creates in a period. It deducts from the operating profit the cost of all the capital, debt and equity:

$$EVA = NOPAT - WACC \times IC = (ROIC - WACC) \times IC$$

- $NOPAT$, $IC$ and $ROIC$ are the terms of the section "ROIC" above.
- $WACC \times IC$ is the **capital charge**, the cost of all the capital.

The company creates value when $EVA > 0$, i.e. when $ROIC > WACC$. 

## NOPAT

## EBITDA

## ROIC

The **return on invested capital** (ROIC) measures how much operating profit the company generates with the capital that it uses. It is the operating profit after taxes (NOPAT) divided by the **invested capital** (IC).

$$ROIC = \frac{NOPAT}{IC} = \frac{EBIT (1 - \tau)}{IC}$$

- $NOPAT = EBIT (1 - \tau)$ is the operating profit after taxes, as if the company had no debt (see [Operating Decisions](01-operating-decisions.md)).
- $\tau$ is the tax rate.
- $IC$ is the invested capital, the funds that the creditors and the shareholders put in the operations of the company.

We can calculate the invested capital from the two sides of the balance sheet. The two calculations give the same value.

- **From the uses of the funds**, the invested capital is the operating fixed assets (net of the depreciation) plus the operating working capital.
- **From the sources of the funds**, the invested capital is the equity plus the net debt, which is the financial debt minus the excess cash.

The numerator and the denominator are consistent. The NOPAT is the profit before the interest, so it belongs to all the providers of funds. The invested capital also includes the funds of all the providers. For this reason the ROIC does not depend on how the company is financed, and we can compare it with the WACC, which is the cost of the same funds.

The ROIC is different from the **return on equity** (ROE), $ROE = \frac{\text{net income}}{\text{equity}}$. The ROE measures the return for the shareholders only, after the interest on the debt. The ROE changes with the debt of the company, so we compare it with the cost of equity $k_E$, not with the WACC.

> [!NOTE]
> The invested capital changes during the year. A common choice is the invested capital at the start of the year, or the average of the values at the start and at the end of the year. The non-operating assets (e.g. financial investments) are not part of the invested capital, because they do not generate the NOPAT.

The example in the section "A Profitable Company Can Destroy Value" calculates a ROIC of $6\%$ and compares it with the ROE.

TODO Buen Ejemplo:
A company with zero grwoth, 1000 revenue 100 proifts and 500 of IC, which is the ROIC?

ROIC = 20%

ROIC = NOPAT / Invested Capital = 100 / 500 = 20%

This assumes the 100 of profit is after-tax operating profit (NOPAT). If it’s pre-tax or net income after interest, you’d need to adjust it first.

Revenue and growth don’t change the ROIC calculation, but they tell you a couple of related things:

Operating margin: 100 / 1,000 = 10%
Capital turnover: 1,000 / 500 = 2.0x, and 10% × 2.0 = 20% ROIC
Reinvestment: with zero growth, the reinvestment rate (growth ÷ ROIC) is 0%. The company doesn’t need to reinvest, so free cash flow equals NOPAT (100).
TODO Buen Ejemplo:


## Growth

## Relation between ROIC and Growth


## A Profitable Company Can Destroy Value

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

## A Growing Company Can Destroy Value Faster

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
- Wikipedia. "Economic Profit." [Online article](https://en.wikipedia.org/wiki/Economic_profit).
- Wikipedia. "Economic Value Added." [Online article](https://en.wikipedia.org/wiki/Economic_value_added).
- Wikipedia. "Risk Premium." [Online article](https://en.wikipedia.org/wiki/Risk_premium).
- Wikipedia. "Risk-Free Rate." [Online article](https://en.wikipedia.org/wiki/Risk-free_rate).
- Wikipedia. "Terminal Value (Finance)." [Online article](https://en.wikipedia.org/wiki/Terminal_value_(finance)).
