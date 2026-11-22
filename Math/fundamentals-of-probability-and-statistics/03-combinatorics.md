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

## 3.3 Diophantine Approximation

**Diophantine approximation** studies how well rational numbers $p/q$ approximate a real number $a$. The name comes from Diophantus of Alexandria, who studied equations with integer solutions. For every $q \geq 1$, the nearest multiple of $1/q$ gives $|a - p/q| \leq 1/(2q)$, and the question is how much smaller the error can be for a small $q$.

### 3.3.1 Problem

**Problem:** given an irrational number $a \in \mathbb{I}$, for every $\varepsilon > 0$ there are $p \in \mathbb{Z}$ and $q \in \mathbb{N}$ with

$$
\left| a - \frac{p}{q} \right| \leq \varepsilon
$$

So we can approximate every irrational number by rational numbers as closely as we want. Decimal truncation already gives this, but the pigeonhole principle gives a much smaller error for the same denominator $q$.

### 3.3.2 Solution with the Pigeonhole Principle

**Step 1.** For any $n \geq 1$, consider the $n + 1$ multiples of $a$.

$$
0, \ a, \ 2a, \ 3a, \ \dots, \ na
$$

**Step 2.** Split each multiple into its integer part $\lfloor ka \rfloor$, the largest integer $\leq ka$, and its fractional part $\lbrace ka \rbrace$.

$$
\lfloor ka \rfloor + \lbrace ka \rbrace = ka \qquad k = 0, 1, \dots, n
$$

This gives $n + 1$ fractional parts in the interval $[0, 1)$.

**Step 3.** Divide $[0, 1)$ into $n$ subintervals of length $1/n$.

$$
I_j = \left[ \frac{j - 1}{n}, \frac{j}{n} \right) \qquad j = 1, \dots, n
$$

There are $n + 1$ fractional parts (the pigeons) and $n$ subintervals (the pigeonholes), so two of them, $\lbrace k_1 a \rbrace$ and $\lbrace k_2 a \rbrace$ with $k_1 < k_2$, are in the same subinterval $I_j$, and $|\lbrace k_2 a \rbrace - \lbrace k_1 a \rbrace| < 1/n$.

**Step 4.** Subtract the two multiples. With $q = k_2 - k_1$ and $p = \lfloor k_2 a \rfloor - \lfloor k_1 a \rfloor$, the integer parts cancel.

$$
|qa - p| = |\lbrace k_2 a \rbrace - \lbrace k_1 a \rbrace| < \frac{1}{n} \qquad 1 \leq q \leq n
$$

**Step 5.** Divide by $q$.

$$
\left| a - \frac{p}{q} \right| < \frac{1}{qn} \leq \frac{1}{n}
$$

For a given $\varepsilon$, take $n \geq 1/\varepsilon$, and the error is less than $\varepsilon$. $\blacksquare$

**Example:** for $a = \sqrt{2}$ and $n = 5$, the subintervals have length $0.2$.

| $k$ | $k\sqrt{2}$ | $\lfloor k\sqrt{2} \rfloor$ | $\lbrace k\sqrt{2} \rbrace$ | Subinterval |
| --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | $I_1 = [0, 0.2)$ |
| 1 | 1.4142 | 1 | 0.4142 | $I_3 = [0.4, 0.6)$ |
| 2 | 2.8284 | 2 | 0.8284 | $I_5 = [0.8, 1)$ |
| 3 | 4.2426 | 4 | 0.2426 | $I_2 = [0.2, 0.4)$ |
| 4 | 5.6569 | 5 | 0.6569 | $I_4 = [0.6, 0.8)$ |
| 5 | 7.0711 | 7 | 0.0711 | $I_1 = [0, 0.2)$ |

The multiples for $k_1 = 0$ and $k_2 = 5$ share the subinterval $I_1$, so $q = 5$ and $p = 7$.

$$
|5\sqrt{2} - 7| \approx 0.0711 < \frac{1}{5} \qquad \left| \sqrt{2} - \frac{7}{5} \right| \approx 0.0142 < \frac{1}{25}
$$
