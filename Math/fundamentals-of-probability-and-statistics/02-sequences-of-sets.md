# 2 Sequences of Sets

## 2.1 Definition of Sequence

Sequences are fundamental in mathematics, and are the basis of the mathematical analysis.

A **sequence** in a set $A$ is a function $a : \mathbb{N} \to A$. The value $a(n)$ is the $n$-th **term** of the sequence, and we write it as $a_n$.

For example, a sequence of real numbers is a function $f : \mathbb{N} \to \mathbb{R}$ that maps each natural number to a term:

$$
\begin{aligned}
f : \mathbb{N} &\to \mathbb{R} \\
1 &\mapsto x_1 \\
2 &\mapsto x_2 \\
3 &\mapsto x_3 \\
&\vdots
\end{aligned}
$$

We denote the full sequence by $\{a_n\}_{n \in \mathbb{N}}$. The order of the terms is important, and the same value can occur more than once.

**Examples:**

- $a_n = \frac{1}{n}$ gives the sequence $1, \frac{1}{2}, \frac{1}{3}, \dots$ in $\mathbb{R}$.
- $a_n = (-1)^n$ gives the sequence $-1, 1, -1, 1, \dots$, which has only two distinct values.

## 2.2 Convergence

Intuitively, a sequence converges to a number $L$ when its terms get as close to $L$ as we want, and stay close, from some index on.

A sequence $\{x_n\}$ of real numbers **converges** to $L \in \mathbb{R}$ if

$$
\forall \varepsilon > 0 \quad \exists n_0 \in \mathbb{N} \mid \forall n \geq n_0 \quad |x_n - L| < \varepsilon
$$

We call $L$ the **limit** of the sequence and write

$$
\lim_{n \to \infty} x_n = L \qquad \text{or} \qquad x_n \to L
$$

How to read the definition:

- $\varepsilon$ is the tolerance: how close to $L$ we require the terms to be. It can be arbitrarily small.
- $n_0$ is the index from which every term is within the tolerance. In general, a smaller $\varepsilon$ requires a larger $n_0$.
- The condition must hold for **all** $n \geq n_0$, not only for some. A finite number of terms at the start does not affect convergence.

If a sequence does not converge to any $L$, we say that it **diverges**.

A convergent sequence has exactly one limit. Two different limits $L \neq L'$ would mean that, as $n$ grows, the terms $x_n$ approach two different values at the same time. This is impossible, because as the terms get closer and closer to $L$, they stay at a distance of almost $|L - L'|$ from $L'$, so they cannot also get arbitrarily close to $L'$.

**Examples:**

- $x_n = \frac{1}{n}$ converges to $0$. For a given $\varepsilon > 0$ we must find $n_0$ such that $|x_n - 0| = \frac{1}{n} < \varepsilon$ for all $n \geq n_0$. Since $\frac{1}{n} < \varepsilon \iff n > \frac{1}{\varepsilon}$ and the terms get smaller as $n$ grows, any $n_0 > \frac{1}{\varepsilon}$ works.
- $x_n = (-1)^n$ diverges. The terms alternate between $-1$ and $1$, so for $\varepsilon = 1$ no $L$ has all terms from some index on within distance $1$ of it.
- $x_n = n$ diverges. The terms grow without bound, and we write $x_n \to \infty$.

## 2.3 Subsequences

A **subsequence** is a sequence obtained from another sequence by keeping only some of its terms, in the same order, and discarding the rest.

Formally, given a sequence $\{x_n\}_{n \in \mathbb{N}}$ and a strictly increasing sequence of natural numbers $n_1 < n_2 < n_3 < \dots$, the sequence $\{x_{n_k}\}_{k \in \mathbb{N}}$ is a subsequence of $\{x_n\}_{n \in \mathbb{N}}$.

The indices must be strictly increasing, so a subsequence cannot repeat a term or change the order of the terms.

If a sequence converges to $L$, every subsequence also converges to $L$. As a consequence, if two subsequences converge to different limits, the sequence diverges.

**Examples:**

- For $x_n = \frac{1}{n}$, the even terms $x_{2k} = \frac{1}{2k}$ give the subsequence $\frac{1}{2}, \frac{1}{4}, \frac{1}{6}, \dots$, which also converges to $0$.
- For $x_n = (-1)^n$, the even terms give the subsequence $1, 1, 1, \dots$, which converges to $1$, and the odd terms give $-1, -1, -1, \dots$, which converges to $-1$. The two limits are different, so $x_n$ diverges.

## 2.4 Inferior and Superior Limits

A sequence that does not converge can still have subsequences that converge. The **inferior limit** and the **superior limit** describe the smallest and the largest values that these subsequences can approach.

The inferior limit of a sequence $\{x_n\}_{n \in \mathbb{N}}$ is denoted by:

$$
\liminf_{n \to \infty} x_n \qquad \text{or} \qquad \varliminf_{n \to \infty} x_n
$$

and the superior limit of a sequence $\{x_n\}_{n \in \mathbb{N}}$ is denoted by:

$$
\limsup_{n \to \infty} x_n \qquad \text{or} \qquad \varlimsup_{n \to \infty} x_n
$$

**Definition:**

For a sequence $\{x_n\}_{n \in \mathbb{N}}$ of real numbers:

- The **inferior limit** is defined by:

$$
\liminf_{n \to \infty} x_n := \lim_{k \to \infty} \left( \inf_{n \geq k} x_n \right)
$$

or

$$
\liminf_{n \to \infty} x_n := \sup_{k \geq 1} \inf_{n \geq k} x_n = \sup \{ \inf \{ x_n : n \geq k \} : k \geq 1 \}
$$

- The **superior limit** is defined by:

$$
\limsup_{n \to \infty} x_n := \lim_{k \to \infty} \left( \sup_{n \geq k} x_n \right)
$$

or

$$
\limsup_{n \to \infty} x_n := \inf_{k \geq 1} \sup_{n \geq k} x_n = \inf \{ \sup \{ x_n : n \geq k \} : k \geq 1 \}
$$

How to read the definition:

- $\inf_{n \geq k} x_n$ is the largest lower bound of the terms from index $k$ on. When $k$ grows, we remove terms from the tail, so this value can only increase.
- $\sup_{n \geq k} x_n$ is the smallest upper bound of the terms from index $k$ on. When $k$ grows, this value can only decrease.
- The limit of a nondecreasing sequence is its supremum, and the limit of a nonincreasing sequence is its infimum. This is why the two forms of each definition are equal.
- A monotone sequence always has a limit, if we accept $\pm\infty$ as a limit. Thus the inferior and the superior limits always exist, also when $x_n$ diverges.
- $\liminf x_n \leq \limsup x_n$, and the sequence converges to $L$ if and only if $\liminf x_n = \limsup x_n = L$.

**Examples:**

- For $x_n = (-1)^n$, the subsequences converge to $-1$ and $1$, so $\liminf x_n = -1$ and $\limsup x_n = 1$. The two values are different, so the sequence diverges.
- For $x_n = (-1)^n \left( 1 + \frac{1}{n} \right)$, the odd terms are negative and approach $-1$ from below, and the even terms are positive and approach $1$ from above. The table shows the infimum and the supremum of the tail for the first values of $k$:

| $k$ | $x_k$ | $\inf_{n \geq k} x_n$ | $\sup_{n \geq k} x_n$ |
| --- | --- | --- | --- |
| $1$ | $-2$ | $-2$ | $\frac{3}{2}$ |
| $2$ | $\frac{3}{2}$ | $-\frac{4}{3}$ | $\frac{3}{2}$ |
| $3$ | $-\frac{4}{3}$ | $-\frac{4}{3}$ | $\frac{5}{4}$ |
| $4$ | $\frac{5}{4}$ | $-\frac{6}{5}$ | $\frac{5}{4}$ |
| $5$ | $-\frac{6}{5}$ | $-\frac{6}{5}$ | $\frac{7}{6}$ |
| $6$ | $\frac{7}{6}$ | $-\frac{8}{7}$ | $\frac{7}{6}$ |
| $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ |
| $\to \infty$ | | $\to -1$ | $\to 1$ |

The graph shows the terms $x_n$ for $n$ from $1$ to $30$, with the supremum and the infimum of the tail as step lines:

![Graph of x_n = (-1)^n (1 + 1/n) for n from 1 to 30, with the supremum and the infimum of the tail as step lines that approach 1 and -1](Attachments/limsup-liminf-sequence.svg)

For each finite $k$, the infimum of the tail is still below $-1$ and the supremum of the tail is still above $1$. Each time that $k$ passes a term that is equal to the infimum or the supremum, that term leaves the tail, and the value moves nearer to its limit. Only in the limit we get

$$
\liminf_{n \to \infty} x_n = -1 \qquad \text{and} \qquad \limsup_{n \to \infty} x_n = 1
$$

Thus, a finite $k$ gives only an approximation of the inferior and the superior limits.

## 2.5 Sequences of Sets

The **power set** of a set $\Omega$ is the set of all subsets of $\Omega$:

$$
\mathcal{P}(\Omega) = \{ A \mid A \subseteq \Omega \}
$$

It always contains $\emptyset$ and $\Omega$, and if $\Omega$ has $n$ elements, $\mathcal{P}(\Omega)$ has $2^n$ elements.

In probability, sets almost never appear in isolation, but in the form of sequences. A **sequence of sets** is a map from $\mathbb{N}$ to all the possible subsets of the sample space, that is, to the power set $\mathcal{P}(\Omega)$, such that:

$$
\begin{aligned}
f : \mathbb{N} &\to \mathcal{P}(\Omega) \\
1 &\mapsto A_1 \\
2 &\mapsto A_2 \\
3 &\mapsto A_3 \\
&\vdots
\end{aligned}
$$

Each term $A_n \subseteq \Omega$ is a set, and we denote the sequence by $\{A_n\}_{n \in \mathbb{N}}$.

**Example:** let $A_n$ be the set

$$
A_n = \left\{ x \in \mathbb{R} : -\frac{1}{n} \leq x \leq \frac{1}{n} \right\}
$$

For $n = 1$ we get the real numbers in the interval $[-1, 1]$, for $n = 2$ we get $\left[ -\frac{1}{2}, \frac{1}{2} \right]$, and so on. In this case we have a sequence of **nested intervals**, where each interval contains the next one:

$$
A_1 \supseteq A_2 \supseteq A_3 \supseteq \dots
$$

![Nested intervals A_n = [-1/n, 1/n] on the real line: A_1 = [-1, 1] contains A_2 = [-1/2, 1/2], which contains A_3 = [-1/3, 1/3]](Attachments/nested-intervals.svg)

## 2.6 Inferior and Superior Limits of Sequences of Sets

For sequences of sets, the inferior and the superior limits have the same structure as for sequences of real numbers. The intersection $\bigcap$ takes the role of $\inf$, and the union $\bigcup$ takes the role of $\sup$.

The inferior limit of a sequence of sets $\{A_n\}_{n \in \mathbb{N}}$ is denoted by:

$$
\liminf_{n \to \infty} A_n \qquad \text{or} \qquad \varliminf_{n \to \infty} A_n
$$

and the superior limit of a sequence of sets $\{A_n\}_{n \in \mathbb{N}}$ is denoted by:

$$
\limsup_{n \to \infty} A_n \qquad \text{or} \qquad \varlimsup_{n \to \infty} A_n
$$

**Definition:**

For a sequence $\{A_n\}_{n \in \mathbb{N}}$ of subsets of $\Omega$:

- The **inferior limit** is defined by:

$$
\liminf_{n \to \infty} A_n := \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n = \bigcap_{n=1}^{\infty} A_n \cup \bigcap_{n=2}^{\infty} A_n \cup \bigcap_{n=3}^{\infty} A_n \cup \dots
$$

  $\omega \in \liminf A_n$ if and only if there is an index $k$ such that $\omega \in A_n$ for all $n \geq k$. That is, $\omega$ is in all the sets $A_n$, with the exception of a finite number of them.

- The **superior limit** is defined by:

$$
\limsup_{n \to \infty} A_n := \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n = \bigcup_{n=1}^{\infty} A_n \cap \bigcup_{n=2}^{\infty} A_n \cap \bigcup_{n=3}^{\infty} A_n \cap \dots
$$

  $\omega \in \limsup A_n$ if and only if for each index $k$ there is an $n \geq k$ such that $\omega \in A_n$. That is, $\omega$ is in an infinite number of the sets $A_n$.

How to read the definition:

- $\bigcap_{n=k}^{\infty} A_n$ contains the elements that are in **all** the sets of the tail from index $k$ on. When $k$ grows, there are fewer sets in the intersection, so this set can only get larger.
- $\bigcup_{n=k}^{\infty} A_n$ contains the elements that are in **at least one** set of the tail from index $k$ on. When $k$ grows, there are fewer sets in the union, so this set can only get smaller.
- An element that is in all the sets from some index on is also in an infinite number of sets, so $\liminf A_n \subseteq \limsup A_n$.

**Examples:**

- For the nested intervals $A_n = \left[ -\frac{1}{n}, \frac{1}{n} \right]$ of section 2.5, each interval contains the next one. Thus for each $k$:

$$
\bigcap_{n=k}^{\infty} A_n = \{0\} \qquad \text{and} \qquad \bigcup_{n=k}^{\infty} A_n = A_k
$$

  The only real number that is in all the intervals is $0$, because for each $x \neq 0$ there is an $n$ with $\frac{1}{n} < |x|$. Thus

$$
\liminf_{n \to \infty} A_n = \bigcup_{k=1}^{\infty} \{0\} = \{0\} \qquad \text{and} \qquad \limsup_{n \to \infty} A_n = \bigcap_{k=1}^{\infty} A_k = \{0\}
$$

  The two limits are equal, so the sequence converges (see section 2.7) and $\lim_{n \to \infty} A_n = \{0\}$.

- For two sets $A$ and $B$, let $A_n = A$ if $n$ is even and $A_n = B$ if $n$ is odd. Each tail contains both $A$ and $B$, so for each $k$:

$$
\bigcap_{n=k}^{\infty} A_n = A \cap B \qquad \text{and} \qquad \bigcup_{n=k}^{\infty} A_n = A \cup B
$$

  Thus $\liminf A_n = A \cap B$ and $\limsup A_n = A \cup B$. If $A \neq B$, the two limits are different, so the sequence does not converge (see section 2.7). This is the same as $x_n = (-1)^n$ for sequences of real numbers.

**Proof: inferior limit of sequences of sets**

We want to prove that the inferior limit, as the set of the elements that are in all the sets $A_n$ with the exception of a finite number of them, is equal to the union of the intersections of the tails:

$$
\liminf_{n \to \infty} A_n = \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n
$$

Two sets are equal if and only if each one of them contains the other one. Thus we prove the two inclusions:

$$
\liminf_{n \to \infty} A_n \subseteq \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n \qquad \text{and} \qquad \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n \subseteq \liminf_{n \to \infty} A_n
$$

**a)** Let

$$
\delta_k = \bigcap_{n=k}^{\infty} A_n \qquad \text{and} \qquad \sigma_k = \bigcup_{n=k}^{\infty} A_n
$$

Observe that:

$$
\delta_1 \subseteq \delta_2 \subseteq \delta_3 \subseteq \dots
$$

$$
\bigcap_{n=1}^{\infty} A_n \subseteq \bigcap_{n=2}^{\infty} A_n \subseteq \bigcap_{n=3}^{\infty} A_n \subseteq \dots
$$

$$
\sigma_1 \supseteq \sigma_2 \supseteq \sigma_3 \supseteq \dots
$$

$$
\bigcup_{n=1}^{\infty} A_n \supseteq \bigcup_{n=2}^{\infty} A_n \supseteq \bigcup_{n=3}^{\infty} A_n \supseteq \dots
$$

The intersection $\delta_{k+1}$ has one set less than $\delta_k$, because it does not contain $A_k$. When $k$ grows, the tail has fewer sets, so the intersection is less restrictive and the set gets bigger $\delta_k \subseteq \delta_{k+1}$. Similarly, the union $\sigma_{k+1}$ has one set less than $\sigma_k$, so $\sigma_k \supseteq \sigma_{k+1}$.

**b)** $\liminf A_n \subseteq \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n$

Let $\omega \in \liminf A_n$. Then there is a $k_0 \in \mathbb{N}$ such that $\omega \in A_n$ for all $n \geq k_0$. Thus $\omega$ is in the intersection $\delta_{k_0}$ of the tail from index $k_0$ on:

$$
\exists k_0 : \omega \in \delta_{k_0} \implies \omega \in \bigcup_{k=1}^{\infty} \delta_k \implies \omega \in \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n
$$

This is true for each $\omega \in \liminf A_n$, so $\liminf A_n \subseteq \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n$.

**c)** $\bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n \subseteq \liminf A_n$

Let $\omega \in \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n$. An element of a union is in at least one of the sets of the union, so there is a $k_0 \in \mathbb{N}$ such that $\omega \in \delta_{k_0}$:

$$
\omega \in \bigcup_{k=1}^{\infty} \delta_k \implies \exists k_0 : \omega \in \delta_{k_0} = \bigcap_{n=k_0}^{\infty} A_n \implies \forall n \geq k_0 \ \omega \in A_n
$$

Thus $\omega$ is in all the sets $A_n$ from index $k_0$ on. The only sets that can be without $\omega$ are $A_1, A_2, \dots, A_{k_0 - 1}$, which are a finite number of sets. Thus $\omega \in \liminf A_n$.

This is true for each $\omega \in \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n$, so $\bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n \subseteq \liminf A_n$.

From b) and c), each set contains the other one, so

$$
\liminf_{n \to \infty} A_n = \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n \qquad \blacksquare
$$

**Proof: superior limit of sequences of sets**

We want to prove that the superior limit, as the set of the elements that are in an infinite number of the sets $A_n$, is equal to the intersection of the unions of the tails:

$$
\limsup_{n \to \infty} A_n = \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n
$$

Two sets are equal if and only if each one of them contains the other one. Thus we prove the two inclusions:

$$
\limsup_{n \to \infty} A_n \subseteq \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n \qquad \text{and} \qquad \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n \subseteq \limsup_{n \to \infty} A_n
$$

**a)** As in the proof of the inferior limit, let

$$
\sigma_k = \bigcup_{n=k}^{\infty} A_n
$$

Then $\bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n = \bigcap_{k=1}^{\infty} \sigma_k$, and $\sigma_1 \supseteq \sigma_2 \supseteq \sigma_3 \supseteq \dots$

**b)** $\limsup A_n \subseteq \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n$

Let $\omega \in \limsup A_n$, so $\omega$ is in an infinite number of the sets $A_n$. Let $k \in \mathbb{N}$ be an index. Only a finite number of sets, $A_1, A_2, \dots, A_{k-1}$, come before $A_k$. Thus at least one of the sets that contain $\omega$ has an index $n \geq k$:

$$
\forall k \ \exists n \geq k : \omega \in A_n \implies \omega \in \sigma_k \ \forall k \implies \omega \in \bigcap_{k=1}^{\infty} \sigma_k \implies \omega \in \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n
$$

This is true for each $\omega \in \limsup A_n$, so $\limsup A_n \subseteq \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n$.

**c)** $\bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n \subseteq \limsup A_n$

Let $\omega \in \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n$. An element of an intersection is in all the sets of the intersection, so $\omega \in \sigma_k$ for all $k \in \mathbb{N}$:

$$
\omega \in \bigcap_{k=1}^{\infty} \sigma_k \implies \omega \in \sigma_k = \bigcup_{n=k}^{\infty} A_n \ \forall k \implies \forall k \ \exists n \geq k : \omega \in A_n
$$

Suppose that $\omega$ is in only a finite number of the sets $A_n$. If $\omega$ is in no set, then $\omega \notin \sigma_1$. If not, let $N$ be the largest index with $\omega \in A_N$. For $k = N + 1$, no set $A_n$ with $n \geq k$ contains $\omega$, so $\omega \notin \sigma_{N+1}$. In the two cases there is a contradiction. Thus $\omega$ is in an infinite number of the sets $A_n$, and $\omega \in \limsup A_n$.

This is true for each $\omega \in \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n$, so $\bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n \subseteq \limsup A_n$.

From b) and c), each set contains the other one, so

$$
\limsup_{n \to \infty} A_n = \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n \qquad \blacksquare
$$

## 2.7 Convergent Sequences of Sets

A sequence of sets $\{A_n\}_{n \in \mathbb{N}}$ is **convergent** if and only if

$$
\limsup_{n \to \infty} A_n = \liminf_{n \to \infty} A_n
$$

In this case, the common set of the superior and the inferior limits is the **limit** of $A_n$:

$$
\lim_{n \to \infty} A_n = \liminf_{n \to \infty} A_n = \limsup_{n \to \infty} A_n
$$


If the inferior and the superior limits of a sequence of sets are different, we say that the sequence has **no limit**.

**Example:** let $\{A_n\}_{n \in \mathbb{N}}$ be the sequence defined by

$$
A_n =
\begin{cases}
[0, 1] & n \text{ odd} \\
[1, 2] & n \text{ even}
\end{cases}
$$

Each tail $A_k, A_{k+1}, A_{k+2}, \dots$ contains both $[0, 1]$ and $[1, 2]$, so the intersection of each tail is $[0, 1] \cap [1, 2] = \{1\}$. Thus the inferior limit is

$$
\liminf_{n \to \infty} A_n = \bigcup_{k=1}^{\infty} \bigcap_{n=k}^{\infty} A_n = \bigcap_{n=1}^{\infty} A_n \cup \bigcap_{n=2}^{\infty} A_n \cup \bigcap_{n=3}^{\infty} A_n \cup \dots = \{1\}
$$

Similarly, the union of each tail is $[0, 1] \cup [1, 2] = [0, 2]$. Thus the superior limit is

$$
\limsup_{n \to \infty} A_n = \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n = \bigcup_{n=1}^{\infty} A_n \cap \bigcup_{n=2}^{\infty} A_n \cap \bigcup_{n=3}^{\infty} A_n \cap \dots = [0, 2]
$$

The inferior limit $\{1\}$ and the superior limit $[0, 2]$ are different, so the sequence has no limit.

## 2.8 Monotone Sequences of Sets

**Definition:**

- $\{A_n\}_{n \in \mathbb{N}}$ is a **monotone increasing** sequence, written $A_n \uparrow$, if

$$
A_n \subseteq A_{n+1} \quad \forall n
$$

- $\{A_n\}_{n \in \mathbb{N}}$ is a **monotone decreasing** sequence, written $A_n \downarrow$, if

$$
A_n \supseteq A_{n+1} \quad \forall n
$$

**Proposition (limit of monotone sequences of sets):**

Every monotone sequence of sets has a limit:

- If $A_n \uparrow$, the limit is

$$
\lim_{n \to \infty} A_n = \bigcup_{n=1}^{\infty} A_n
$$

- If $A_n \downarrow$, the limit is

$$
\lim_{n \to \infty} A_n = \bigcap_{n=1}^{\infty} A_n
$$

## 2.9 Properties of the Limits of Sequences of Sets

In this section, $\varlimsup A_n$ is the superior limit and $\varliminf A_n$ is the inferior limit of $\{A_n\}_{n \in \mathbb{N}}$, and $B$ is a set.

**a)** The limits of a sequence can be found from the limits of its even terms $A_{2n}$ and its odd terms $A_{2n-1}$:

$$
\begin{aligned}
\varlimsup A_n &= \varlimsup A_{2n} \cup \varlimsup A_{2n-1} \\
\varliminf A_n &= \varliminf A_{2n} \cap \varliminf A_{2n-1}
\end{aligned}
$$

An element is in an infinite number of the sets $A_n$ if and only if it is in an infinite number of the even sets or of the odd sets. An element is in all the sets from some index on if and only if this is true for the even sets and for the odd sets.

**b)** The limits of the differences $B \setminus A_n$:

$$
\begin{aligned}
\varlimsup (B \setminus A_n) &= B \setminus \varliminf A_n \\
\varliminf (B \setminus A_n) &= B \setminus \varlimsup A_n
\end{aligned}
$$

**c)** The complement changes the superior limit into the inferior limit, and the inferior limit into the superior limit:

$$
\begin{aligned}
\left( \varlimsup A_n \right)^c &= \varliminf A_n^c \\
\left( \varliminf A_n \right)^c &= \varlimsup A_n^c
\end{aligned}
$$

This follows from De Morgan's laws, because the complement changes each union into an intersection and each intersection into a union.

**d)** The limits of the unions and the intersections of two sequences $\{A_n\}_{n \in \mathbb{N}}$ and $\{B_n\}_{n \in \mathbb{N}}$:

$$
\begin{aligned}
\varlimsup (A_n \cup B_n) &= \varlimsup A_n \cup \varlimsup B_n \\
\varliminf (A_n \cap B_n) &= \varliminf A_n \cap \varliminf B_n
\end{aligned}
$$
