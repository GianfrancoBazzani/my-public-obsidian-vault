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

## 2.3 Sequences of Sets

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
