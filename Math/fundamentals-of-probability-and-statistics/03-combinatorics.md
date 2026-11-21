# 3 Combinatorics

## 3.1 Introduction

**Combinatorics** is the branch of mathematics that studies the enumeration, combination, and permutation of the elements of sets, and the relations that characterize their properties. Its most classical part, **enumerative combinatorics**, counts the elements of finite sets that satisfy given conditions, with an answer as a closed formula, a recurrence relation, a generating function, or an asymptotic estimate.

The boundaries of the field are not universally agreed upon. In a broader sense, the term also covers graph theory and other areas of discrete mathematics, and the counting part is then called **enumeration**.

In probability, combinatorics counts the outcomes of a finite sample space $\Omega$. If all the outcomes are equally likely, then $P(A) = |A| / |\Omega|$, where $|A|$ is the number of elements of $A$.

## 3.2 Pigeonhole Principle

### 3.2.1 Statement

If $n$ objects go into $m < n$ boxes, then at least one box contains at least two objects. The name comes from $n$ pigeons in $m$ pigeonholes. Dirichlet stated it in 1834 as the *Schubfachprinzip* (**drawer principle**), so it is also called **Dirichlet's box principle**, but the idea already appears in a book of 1624 attributed to Jean Leurechon.

In its simplest form, if $m + 1$ pigeons fly into $m$ pigeonholes, then at least two pigeons share a pigeonhole.

Equivalently, if $A$ and $B$ are finite sets with $|A| > |B|$, then no function $f : A \to B$ is injective, so $f(a_1) = f(a_2)$ for some $a_1 \neq a_2$.

**Proof**

If each box contains at most one object, then there are at most $m < n$ objects, which is a contradiction. $\blacksquare$

The principle proves that such a box exists, but it does not tell which one.

### 3.2.2 Generalized Pigeonhole Principle

If $n$ objects go into $m$ boxes, then at least one box contains at least $\lceil n/m \rceil$ objects, where $\lceil x \rceil$ is the smallest integer $\geq x$. For $n > m$, $\lceil n/m \rceil \geq 2$ gives the simple principle.

In its simplest form, if $km + 1$ pigeons fly into $m$ pigeonholes, then at least $k + 1$ pigeons share a pigeonhole, because $\lceil (km + 1)/m \rceil = k + 1$.

**Proof**

If each box contains at most $\lceil n/m \rceil - 1$ objects, then, because $\lceil x \rceil - 1 < x$ for every real $x$, the total number of objects is at most

$$
m \left( \left\lceil \frac{n}{m} \right\rceil - 1 \right) < m \cdot \frac{n}{m} = n
$$

which is a contradiction. $\blacksquare$

**Example:** with 12 birth months, at least $\lceil 100/12 \rceil = 9$ of 100 people share a birth month.

### 3.2.3 Examples

**Birthdays:** with 366 possible birthdays (February 29 included), at least two of 367 people share a birthday. This certainty needs 367 people, but the probability of a shared birthday is already above 50% with 23 people (the birthday problem).

**Socks:** among three socks taken without looking from a drawer of black and blue socks, at least two have the same color (three objects, two boxes).

**Hairs:** a human head has about 150,000 hairs on average, and we assume that no person has more than 1,000,000, so there are 1,000,001 possible numbers of hairs (0 to 1,000,000). London has more than 9,000,000 people, so at least $\lceil 9{,}000{,}000 / 1{,}000{,}001 \rceil = 9$ of them have exactly the same number of hairs.

**Handshakes:** in a group of $n > 1$ people who shake hands among themselves, at least two people have the same number of handshakes. Each person has between $0$ and $n - 1$ handshakes ($n$ values), but $0$ and $n - 1$ cannot both occur, because a person with $n - 1$ handshakes shakes hands with everyone. So the $n$ people go into at most $n - 1$ boxes.


**Example:** for $\alpha = \sqrt{2}$ and $N = 5$, the boxes have length $0.2$.

| $k$ | $k\sqrt{2}$ | $\lfloor k\sqrt{2} \rfloor$ | $\lbrace k\sqrt{2} \rbrace$ | Box |
| --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | $[0, 0.2)$ |
| 1 | 1.4142 | 1 | 0.4142 | $[0.4, 0.6)$ |
| 2 | 2.8284 | 2 | 0.8284 | $[0.8, 1)$ |
| 3 | 4.2426 | 4 | 0.2426 | $[0.2, 0.4)$ |
| 4 | 5.6569 | 5 | 0.6569 | $[0.6, 0.8)$ |
| 5 | 7.0711 | 7 | 0.0711 | $[0, 0.2)$ |

The multiples for $k = 0$ and $k = 5$ share the box $[0, 0.2)$, so $q = 5$ and $p = 7$.

$$
|5\sqrt{2} - 7| \approx 0.0711 < \frac{1}{5} \qquad \left| \sqrt{2} - \frac{7}{5} \right| \approx 0.0142 < \frac{1}{25}
$$

### 3.3.3 Dirichlet's Approximation Theorem

The solution never uses that $\alpha$ is irrational, and $q \leq N$ gives $1/(qN) \leq 1/q^2$. So for every real number $\alpha$ and every integer $N \geq 1$, there are integers $p$ and $q$ with $1 \leq q \leq N$ and

$$
|q\alpha - p| < \frac{1}{N} \qquad \text{so} \qquad \left| \alpha - \frac{p}{q} \right| < \frac{1}{qN} \leq \frac{1}{q^2}
$$

This is **Dirichlet's approximation theorem**, which Dirichlet proved around 1842 with the pigeonhole principle.

### 3.3.4 Irrational and Rational Numbers

If $\alpha$ is irrational, there are infinitely many fractions $p/q$ with $|\alpha - p/q| < 1/q^2$.

**Proof**

Suppose that there are only finitely many, $p_1/q_1, \dots, p_r/q_r$ in lowest terms. Because $\alpha$ is irrational, each $|q_i\alpha - p_i| > 0$, so we can take $N$ with $1/N < |q_i\alpha - p_i|$ for every $i$. Dirichlet's theorem gives $p/q$ with $|\alpha - p/q| < 1/q^2$ and $|q\alpha - p| < 1/N$. If $p/q = p_i/q_i$, then $(p, q) = c(p_i, q_i)$ for an integer $c \geq 1$, and $|q\alpha - p| = c|q_i\alpha - p_i| > 1/N$. So $p/q$ is a new fraction, which is a contradiction. $\blacksquare$

If $\alpha = a/b$ is rational, then for every $p/q \neq a/b$

$$
\left| \frac{a}{b} - \frac{p}{q} \right| = \frac{|aq - bp|}{bq} \geq \frac{1}{bq}
$$

so $|\alpha - p/q| < 1/q^2$ needs $q < b$, and only finitely many fractions satisfy it.

### 3.3.5 Examples and Limits

**Example:** for $\pi = 3.14159\dots$, the fractions $22/7$ and $355/113$ satisfy the bound.

$$
\left| \pi - \frac{22}{7} \right| \approx 1.26 \times 10^{-3} < \frac{1}{7^2} \approx 2.04 \times 10^{-2} \qquad \left| \pi - \frac{355}{113} \right| \approx 2.67 \times 10^{-7} < \frac{1}{113^2} \approx 7.83 \times 10^{-5}
$$

The bound $1/q^2$ is almost the best possible.

- **Constant:** Hurwitz proved in 1891 that every irrational $\alpha$ has infinitely many fractions with $|\alpha - p/q| < 1/(\sqrt{5} q^2)$. For the golden ratio $\varphi = (1 + \sqrt{5})/2$, no constant larger than $\sqrt{5}$ works.
- **Exponent:** Roth proved in 1955 that, for an irrational algebraic number $\alpha$ and every $\varepsilon > 0$, only finitely many fractions satisfy $|\alpha - p/q| < 1/q^{2 + \varepsilon}$. He received the Fields Medal in 1958 for this result.
