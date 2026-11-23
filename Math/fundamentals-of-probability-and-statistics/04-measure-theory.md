# 4 Measure Theory

## 4.1 The Problem of Measure

Length, area, and volume give a size to subsets of $\mathbb{R}$, $\mathbb{R}^2$, and $\mathbb{R}^3$. For simple sets, such as intervals, rectangles, and boxes, the size is clear. For other sets, such as the rational numbers in $[0, 1]$, it is not. Probability has the same need, because an event is a subset of the sample space $\Omega$ and its probability is a size of that subset.

The main question of measure theory is the following one. On which collection $\mathcal{A}$ of subsets of $\mathbb{R}^n$ can we define a non-trivial function

$$
\mu : \mathcal{A} \to [0, +\infty)
$$

that gives a value to each set of $\mathcal{A}$ and satisfies the axioms below? Non-trivial means that $\mu$ is not $0$ for all sets. We work in $\mathbb{R}$, where the value of a set is its length.

### 4.1.1 Axiom of Length

**a)** Let $I = (a, b]$. The length of $I$ is

$$
\text{length}((a, b]) = |b - a|
$$

From now on we call the length $\lambda$, which is the usual symbol of the Lebesgue measure. The intervals are half-open because two adjacent intervals, such as $(a, c]$ and $(c, b]$, are disjoint and their union is $(a, b]$.

### 4.1.2 Axiom of Additivity

**b)** If $A_1, A_2, \dots, A_n$ are pairwise disjoint sets, that is, $A_i \cap A_j = \emptyset$ for $i \neq j$, then

$$
\lambda(A_1 \cup A_2 \cup \dots \cup A_n) = \lambda(A_1) + \lambda(A_2) + \dots + \lambda(A_n)
$$

This property is **additivity**. The length of a whole is the sum of the lengths of its pieces. The sets must be disjoint, because the sum counts an overlap more than one time. For example, $\lambda((0, 2] \cup (1, 3]) = \lambda((0, 3]) = 3$, but $\lambda((0, 2]) + \lambda((1, 3]) = 4$.

### 4.1.3 Continuity for Increasing Sequences

**c)** If $\{A_n\}_{n \in \mathbb{N}}$ is a monotone increasing sequence of subsets of $\mathbb{R}$, that is,

$$
A_n \subseteq A_{n+1} \quad \forall n
$$

then

$$
\lambda\left(\bigcup_{n \in \mathbb{N}} A_n\right) = \lim_{n \to \infty} \lambda(A_n)
$$

This property is **continuity** for increasing sequences. The union is the limit of the increasing sequence (see [2 Sequences of Sets](02-sequences-of-sets.md)), so the axiom says that $\lambda(\lim A_n) = \lim \lambda(A_n)$, as for a continuous function. For example, $A_n = \left(0, 1 - \frac{1}{n}\right]$ increases to $(0, 1)$, and $\lambda(A_n) = 1 - \frac{1}{n} \to 1 = \lambda((0, 1))$.

Axioms b) and c) together are equivalent to **countable additivity**, which is additivity for an infinite sequence of pairwise disjoint sets.

### 4.1.4 Subtractivity

**d)** If $A_2 \subseteq A_1$ and $\lambda(A_2) < \infty$, then

$$
\lambda(A_1 \setminus A_2) = \lambda(A_1) - \lambda(A_2)
$$

This property follows from additivity, because $A_1$ is the disjoint union of $A_2$ and $A_1 \setminus A_2$. The condition $\lambda(A_2) < \infty$ is necessary because a length can be infinite, such as $\lambda(\mathbb{R}) = \infty$, and $\infty - \infty$ has no value.

### 4.1.5 Invariance under Translations

A length must not change when we move a set. For $A \subseteq \mathbb{R}$ and $x \in \mathbb{R}$,

$$
\lambda(A + x) = \lambda(A)
$$

where $A + x = \{a + x : a \in A\}$. In $\mathbb{R}^n$, area and volume must also be invariant under rotations.

### 4.1.6 Answer to the Problem

The collection $\mathcal{A}$ is not the power set $\mathcal{P}(\mathbb{R})$. No function can give a consistent value to every subset of $\mathbb{R}$ and also satisfy axioms a) to d) and invariance under translations. The sets that have a value are the **measurable sets**, and the other sets are **non-measurable**. The classic example of a non-measurable set is the **Vitali set** (1905).

## 4.2 Tools for Measure Theory

To assign measures to sets, which is in essence what probability does, we must answer two questions.

1. **On which sets can we measure?** This question leads to the notion of a **σ-algebra** of sets $\Sigma$, the collection of the subsets of $\Omega$ that we can measure. We need this collection because we cannot measure all the subsets of $\mathbb{R}$.
2. **Which measure do we use?** This question leads to the notion of a **probability measure** $P$, the function that gives a probability to each set of $\Sigma$.

The triple $(\Omega, \Sigma, P)$ is a **probability space**. It is the same structure as $(\Omega, \mathcal{F}, P)$ (see [1 Introduction to Probability and Set Theory](01-introduction-to-probability-and-set-theory.md)), with $\Sigma$ in place of $\mathcal{F}$.

For example, for a fair die, $\Omega = \lbrace 1, 2, 3, 4, 5, 6 \rbrace$ is finite, so we can measure all its subsets and $\Sigma = \mathcal{P}(\Omega)$.

## 4.3 σ-Algebras of Sets

We want the largest possible collections of sets on which we can measure in a **consistent** way. The collection $\mathcal{P}(\Omega)$ of all the subsets is not always possible. These collections must be **closed** (or stable) under countable unions and under complements, that is, these operations on sets of the collection give sets of the collection.

We need these properties because the axioms of measure use these sets. Countable additivity measures a countable union, and subtractivity measures the complement $\Omega \setminus A$. In terms of events, $A^c$ means that $A$ does not occur, and $\bigcup_n A_n$ means that at least one $A_n$ occurs.

Some questions in probability need these two properties.

- **Infinite coin tosses.** What is the probability that at least one of infinitely many tosses of a fair coin gives heads? If $H_n$ is the event "toss $n$ gives heads", this event is the countable union $\bigcup_{n=1}^{\infty} H_n$. Its probability is $1$, because the probability of no heads in the first $n$ tosses is $(1/2)^n \to 0$.
- **Markov chains.** A Markov chain moves at random from state to state, and the next state depends only on the present state. What is the probability that the chain visits a given state at some step, for example the extinction of an epidemic? This event is the countable union over $n$ of the events "the chain is in this state at step $n$".
- **Application letters.** We found the probability that all five letters go to the wrong banks from its complement, the event that at least one letter goes to the correct bank (see [3 Combinatorics](03-combinatorics.md)).

### 4.3.1 Definition of σ-Algebra

The structure of subsets of $\Omega$ on which we can measure in a consistent way is the **σ-algebra**. Given a set $\Omega$, a σ-algebra on $\Omega$ is a non-empty collection $\Sigma$ of subsets of $\Omega$ with two properties.

- **Closed under complements.** If $A \in \Sigma$, then $A^c \in \Sigma$.
- **Closed under countable unions.** If $\lbrace A_n \rbrace_{n \in \mathbb{N}}$ is a countable collection of sets of $\Sigma$, then $\bigcup_{n \in \mathbb{N}} A_n \in \Sigma$.

The collection must be non-empty, because the empty collection has both properties but contains no set. Then $\Omega$ and $\emptyset$ are always in $\Sigma$. For a set $A \in \Sigma$, the union of $A$ and $A^c$ gives $\Omega \in \Sigma$, and the complement of $\Omega$ gives $\emptyset \in \Sigma$.

For example, for a die, $\Sigma = \lbrace \emptyset, \lbrace 1, 3, 5 \rbrace, \lbrace 2, 4, 6 \rbrace, \Omega \rbrace$ is a σ-algebra on $\Omega = \lbrace 1, 2, 3, 4, 5, 6 \rbrace$. With this collection we can measure the events "odd" and "even", but not the event "the result is 6".
