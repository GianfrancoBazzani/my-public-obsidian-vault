# Capitalization Process

## Definitions

### Capitalization

The capitalization is the process where an investor invests an initial capital with the goal of generating interest in the future. An investor gives an initial capital $C_0$ at the present time. The investor receives a larger capital $C_t$ at a future time $t$. The difference $I = C_t - C_0$ is the interest. The interest is the price of the use of the money during the term $t$.

![](Attachments/capitalization-discount.svg)

Notation:

- $C_0$: initial capital (present value).
- $C_t$: accumulated capital or future value at time $t$.
- $t$: term or elapsed time, in years.
- $m$: number of capitalization periods per year (compounding frequency).
- $r_s$: simple interest rate.
- $r_c$: compound interest rate.
- $r$: continuous interest rate.

### Discount

The discount is the inverse process of the capitalization. It determines the present value $C_0$ of a capital $C_t$ that an investor receives or pays at a future time $t$. The present value is the future capital minus the interest that the capital would produce during the term $t$. The difference $D = C_t - C_0$ is the discount.

> It answers the following question: "Which capital $C_0$ must I invest in the present to obtain a specific capital $C_t$ in the future?"

## Simple Capitalization

In the simple capitalization, we always compute the interest over the initial capital. The generated interest is not reinvested.

The formula of simple capitalization:

$C_t = C_0 (1 + r_s t)$

The formula of simple discount:

$C_0 = \frac{C_t}{1 + r_s t}$

> The discount formula is the capitalization formula solved for $C_0$. The factor $(1 + r_s t)$ is the growth factor of the capital during the term $t$. Capitalization multiplies the present capital by this factor to move it forward in time. Discount divides the future capital by the same factor to move it back in time. The division undoes the growth, so $C_0$ is the amount that grows exactly to $C_t$.

## Compound Capitalization

In the compound capitalization, the interest is reinvested at the end of each period. The reinvested interest becomes part of the capital. In the next period, the interest is computed on this larger capital. The interest generates more interest, so the capital grows in an exponential way with the term $t$.

The formula of compound capitalization:

$C_t = C_0 (1 + \frac{r_c}{m})^{mt}$

The formula of compound discount:

$C_0 = \frac{C_t}{(1 + \frac{r_c}{m})^{mt}}$

> The rate $r_c$ is usually defined as the nominal annual rate, so the rate of one period is $r_c / m$. Each year contains $m$ periods, and the term contains $t$ years. Therefore the term contains $m \cdot t$ periods in total.

### Compound Capitalization Proof

In compound capitalization, at the end of each period, the capital receives interest equal to $\frac{r_c}{m}$ times the current capital. If we define the compound capitalization as $f(mt)$, where $t$ is the time in years and $m$ is the number of compounding periods per year (the unit of $m$ is year$^{-1}$), we observe a recursive behavior:

$f(mt)|_{t=0} = C_0$

$f(mt)|_{t=\frac{1}{m}}= C_0 +  C_0 \frac{r_c}{m} = C_0 (1 + \frac{r_c}{m})$

$f(mt)|_{t=\frac{2}{m}} = C_0 +  C_0 \frac{r_c}{m} + (C_0 +  C_0 \frac{r_c}{m})\frac{r_c}{m} = C_0 (1 + \frac{r_c}{m})(1 + \frac{r_c}{m}) =  C_0 (1 + \frac{r_c}{m})^2$

$\vdots$

Let $n = mt$, where $n$ is the number of compounding periods in the term (years times the number of compounding periods per year). By definition, for $n \in \mathbb{N}$, $n \geq 1$:

$f(mt) = f(m(t - \frac{1}{m})) + f(m(t - \frac{1}{m})) \frac{r_c}{m} = f(m(t - \frac{1}{m})) (1 + \frac{r_c}{m})$

In terms of $n$:

$f(n) = f(n-1)(1 + \frac{r_c}{m})$

Assume, for some $n \geq 1$:

$f(n-1) = C_0(1 + \frac{r_c}{m})^{n-1}$.

Then:

$f(n) = f(n-1)(1 + \frac{r_c}{m}) = C_0(1 + \frac{r_c}{m})^{n-1}(1 + \frac{r_c}{m}) = C_0(1 + \frac{r_c}{m})^n$.

With $f(0) = C_0$ as the base case, the formula holds for all $n \in \mathbb{N}$ by induction.

Therefore, for all $t \geq 0$ such that $mt \in \mathbb{N}$:

$C_t = f(mt) = C_0 (1 + \frac{r_c}{m})^{mt}$

## Continuous Capitalization

Continuous capitalization is the limit case of the compound capitalization when $m$ tends to infinity ($m \to \infty$). The capitalization happens an infinite number of times during the term $t$. The length of each period $1/m$ tends to zero, so the capital is compounded continuously: at every instant, the interest is reinvested and it becomes part of the capital. There is no waiting time between one capitalization and the next one.

$C_t = \lim_{m \to \infty} C_0 (1 + \frac{r}{m})^{mt} = C_0 e^{r t}$

The formula of continuous discount:

$C_0 = C_t e^{-rt}$

### Derivation of the Growth Factor $e^{rt}$

The derivation uses the definition of the number $e$:

$e = \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^{n} \approx 2.71828$

The growth factor $(1 + \frac{r}{m})^{mt}$ has the same shape.

**Step 1: substitute $n = \frac{m}{r}$ in the limit.** This step needs $r > 0$. If $r > 0$, then $n \to \infty$ when $m \to \infty$. With this substitution, $\frac{r}{m} = \frac{1}{n}$ and $mt = nrt$.

$C_t = \lim_{m \to \infty} C_0 (1 + \frac{r}{m})^{mt} = C_0 \lim_{n \to \infty} \left[\left(1 + \frac{1}{n}\right)^{n}\right]^{rt}$

**Step 2: replace the limit with the definition of $e$.** The function $x^{rt}$ is continuous for $x > 0$, so the limit moves inside the brackets. The part inside the brackets is the definition of $e$. The exponent $rt$ does not depend on $n$, so it stays.

$C_t = C_0 \left[\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^{n}\right]^{rt} = C_0 \, e^{rt}$

**Intuition.** In each period, the capital grows by a small fraction $r/m$. When $m$ grows, the periods become shorter and the fraction per period becomes smaller. There are more periods, but each one adds less. These two effects do not cancel exactly: the reinvested interest is a little larger with more periods. The total growth increases with $m$, but it converges to $e^{rt}$.

Reference: [Continuous compounding explained (where e comes from?)](https://www.youtube.com/watch?v=pg827uDPFqA)

## Applications of Each Capitalization Type

Simple capitalization is commonly used in short-term deposits and interbank swaps, which quote a simple interest rate. It is also used to build the very short end of the yield curve. In general, this capitalization type is used when the reinvestment of the interest is not relevant.

Compound capitalization is the most common type in the market for medium-term and long-term operations. Bonds, loans, and interest rate swaps use compound rates. Over a long term, the reinvestment of the interest is relevant, so the simple formula understates the growth of the capital.

Continuous capitalization is a theoretical construct, but most mathematical models in finance use it. It appears especially in models for the valuation of derivatives and, in general, in models that use differential calculus, such as the Black-Scholes framework. The exponential $e^{rt}$ is easy to differentiate and to integrate, so it simplifies the formulas of these models.

## Interest Rates Equivalence

Two interest rates are equivalent when they produce the same future capital $C_t$ from the same initial capital $C_0$ over the same term $t$, each one under its own capitalization type. The equivalence lets us compare rates that use different capitalization types, or replace one type with another, without altering the future capital.

> It answers the following question: "Given a rate under one capitalization type, which rate must I apply under another capitalization type to obtain the same capital $C_t$ after a term $t$?"

To find the equivalent rate, set the two capitalization formulas equal and solve for the unknown rate. The initial capital $C_0$ cancels, so the equivalence does not depend on the amount invested.

### 1. Between two compound interest rates

$C_0 \left(1 + \frac{r_{c1}}{m_1}\right)^{m_1 t} = C_0 \left(1 + \frac{r_{c2}}{m_2}\right)^{m_2 t} \rightarrow r_{c2} = m_2 \left[ \left(1 + \frac{r_{c1}}{m_1}\right)^{\frac{m_1}{m_2}} - 1 \right]$

### 2. Between compound and continuous

$C_0 \left(1 + \frac{r_c}{m}\right)^{m t} = C_0 e^{rt} \rightarrow r = m \ln\left(1 + \frac{r_c}{m}\right) \Leftrightarrow r_c = m \left(e^{\frac{r}{m}} - 1\right)$

### 3. Between simple and compound

$C_0 (1 + r_s t) = C_0 \left(1 + \frac{r_c}{m}\right)^{m t} \rightarrow r_s = \frac{1}{t}  \left[ (1 + \frac{r_c}{m} )^{mt} - 1 \right] \Leftrightarrow r_c = m  \left[ (1 + r_s t)^{\frac{1}{mt}} - 1 \right]$

### 4. Between simple and continuous

$C_0 (1 + r_s t) = C_0 e^{rt} \rightarrow r_s = \frac{e^{rt} - 1}{t} \Leftrightarrow r = \frac{1}{t} \ln (1 + r_s t)$