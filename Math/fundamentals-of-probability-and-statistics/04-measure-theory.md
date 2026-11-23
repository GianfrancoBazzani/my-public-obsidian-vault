# 4 Measure Theory

## 4.1 The Problem of Measure

Length, area, and volume give a size to subsets of $\mathbb{R}$, $\mathbb{R}^2$, and $\mathbb{R}^3$. For simple sets, such as intervals, rectangles, and boxes, the size is clear. For other sets, such as the rational numbers in $[0, 1]$, it is not. Probability has the same need, because an event is a subset of the sample space $\Omega$ and its probability is a size of that subset.

The main question of measure theory is the following one. On which class $\mathcal{A}$ of subsets of $\mathbb{R}^n$ can we define a non-trivial function

$$
\mu : \mathcal{A} \to [0, +\infty)
$$

that gives a value to each set of $\mathcal{A}$ and satisfies the axioms below?

- $\mathcal{A}$ is a class of sets, that is, a set whose elements are subsets of $\mathbb{R}^n$. The function $\mu$ takes a set as input and gives a number as output.
- **Non-trivial** means that $\mu$ is not $0$ for all sets. The function $\mu \equiv 0$ satisfies the axiom of additivity, but it measures nothing.
- The values are non-negative, because a size cannot be negative. For now they are also finite. A set such as $\mathbb{R}$ itself has an infinite length, so the complete theory also allows the value $+\infty$.

We work in $\mathbb{R}$, where the size of a set is its length. In $\mathbb{R}^n$ the same ideas apply, with boxes in place of intervals.

### 4.1.1 Axiom of Length

**a)** Let $I = (a, b]$ with $a \leq b$. The length of $I$ is

$$
\text{length}((a, b]) = |b - a| = b - a
$$

From now on we call the length $\lambda$, after Henri Lebesgue, who defined it for a very large class of sets in his thesis of 1902. The function that satisfies all the axioms is the **Lebesgue measure**, and $\lambda$ is its usual symbol.

The intervals are **half-open**, open on the left and closed on the right, because they divide and join without overlaps and without gaps. For $a < c < b$,

$$
(a, b] = (a, c] \cup (c, b] \qquad (a, c] \cap (c, b] = \emptyset
$$

With closed intervals, $[a, c]$ and $[c, b]$ have the point $c$ in common. With open intervals, $(a, c) \cup (c, b)$ does not contain $c$. In the same way, the half-open intervals $(n, n + 1]$ with $n \in \mathbb{Z}$ divide all of $\mathbb{R}$ into disjoint pieces of length $1$.

### 4.1.2 Axiom of Additivity

**b)** If $A_1, A_2, \dots, A_n$ are pairwise disjoint sets, that is, $A_i \cap A_j = \emptyset$ for $i \neq j$, then

$$
\lambda(A_1 \cup A_2 \cup \dots \cup A_n) = \lambda(A_1) + \lambda(A_2) + \dots + \lambda(A_n)
$$

This property is **additivity**, or finite additivity, because the number of sets is finite. It says that the length of a whole is the sum of the lengths of its pieces, as when we cut a stick into parts.

**Examples:**

- $\lambda((0, 1] \cup (2, 5]) = \lambda((0, 1]) + \lambda((2, 5]) = 1 + 3 = 4$.
- The axiom of length is consistent with additivity. For $a < c < b$, $\lambda((a, c]) + \lambda((c, b]) = (c - a) + (b - c) = b - a = \lambda((a, b])$.
- The sets must be disjoint. The union of $(0, 2]$ and $(1, 3]$ is $(0, 3]$, of length $3$, but $\lambda((0, 2]) + \lambda((1, 3]) = 4$, because the sum counts the overlap $(1, 2]$ two times.

**Consequences:**

- **Monotonicity.** If $A \subseteq B$ and $B \setminus A$ is also in $\mathcal{A}$, then $B$ is the disjoint union of $A$ and $B \setminus A$. Additivity gives $\lambda(B) = \lambda(A) + \lambda(B \setminus A)$, and since $\lambda(B \setminus A) \geq 0$, we get $\lambda(A) \leq \lambda(B)$.
- **Points have length $0$.** If $\{a\}$ is in $\mathcal{A}$, then $\{a\} \subseteq (a - \varepsilon, a]$ for each $\varepsilon > 0$, so monotonicity gives $0 \leq \lambda(\{a\}) \leq \varepsilon$. Since $\varepsilon$ is arbitrary, $\lambda(\{a\}) = 0$. As a result, $[a, b]$, $(a, b)$, $[a, b)$, and $(a, b]$ all have the same length $b - a$.
