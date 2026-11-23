# 4 Measure Theory

## 4.1 The Problem of Measure

Length, area, and volume give a size to subsets of $\mathbb{R}$, $\mathbb{R}^2$, and $\mathbb{R}^3$. For simple sets, such as intervals, rectangles, and boxes, the size is clear. For other sets, such as the rational numbers in $[0, 1]$, it is not. Probability has the same need, because an event is a subset of the sample space $\Omega$ and its probability is a size of that subset.

The main question of measure theory is the following one. On which class $\mathcal{A}$ of subsets of $\mathbb{R}^n$ can we define a non-trivial function

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

The class $\mathcal{A}$ is not the power set $\mathcal{P}(\mathbb{R})$. No function can give a consistent value to every subset of $\mathbb{R}$ and also satisfy axioms a) to d) and invariance under translations. The sets that have a value are the **measurable sets**, and the other sets are **non-measurable**. The classic example of a non-measurable set is the **Vitali set** (1905).

## 4.2 Tools for Measure Theory

To assign measures to sets, which is in essence what probability does, we must answer two questions.

1. **On which sets can we measure?** This question leads to the notion of a **σ-algebra** of sets $\Sigma$, the class of the subsets of $\Omega$ that we can measure. We need this class because we cannot measure all the subsets of $\mathbb{R}$.
2. **Which measure do we use?** This question leads to the notion of a **probability measure** $P$, the function that gives a probability to each set of $\Sigma$.

The triple $(\Omega, \Sigma, P)$ is a **probability space**. It is the same structure as $(\Omega, \mathcal{F}, P)$ (see [1 Introduction to Probability and Set Theory](01-introduction-to-probability-and-set-theory.md)), with $\Sigma$ in place of $\mathcal{F}$.

For example, for a fair die, $\Omega = \lbrace 1, 2, 3, 4, 5, 6 \rbrace$ is finite, so we can measure all its subsets and $\Sigma = \mathcal{P}(\Omega)$.

## 4.3 σ-Algebras of Sets

We want the largest possible classes of sets on which we can measure in a **consistent** way. The class $\mathcal{P}(\Omega)$ of all the subsets is not always possible. These classes must be **closed** (or stable) under countable unions and under complements, that is, these operations on sets of the class give sets of the class.

We need these properties because the axioms of measure use these sets. Countable additivity measures a countable union, and subtractivity measures the complement $\Omega \setminus A$. In terms of events, $A^c$ means that $A$ does not occur, and $\bigcup_n A_n$ means that at least one $A_n$ occurs.

Some questions in probability need these two properties.

- **Infinite coin tosses.** What is the probability that at least one of infinitely many tosses of a fair coin gives heads? If $H_n$ is the event "toss $n$ gives heads", this event is the countable union $\bigcup_{n=1}^{\infty} H_n$. Its probability is $1$, because the probability of no heads in the first $n$ tosses is $(1/2)^n \to 0$.
- **Markov chains.** A Markov chain moves at random from state to state, and the next state depends only on the present state. What is the probability that the chain visits a given state at some step, for example the extinction of an epidemic? This event is the countable union over $n$ of the events "the chain is in this state at step $n$".
- **Application letters.** We found the probability that all five letters go to the wrong banks from its complement, the event that at least one letter goes to the correct bank (see [3 Combinatorics](03-combinatorics.md)).

### 4.3.1 Definition of σ-Algebra

The structure of subsets of $\Omega$ on which we can measure in a consistent way is the **σ-algebra**. Given a set $\Omega$, a σ-algebra on $\Omega$ is a non-empty class $\Sigma$ of subsets of $\Omega$ with two properties.

- **Closed under complements.** If $A \in \Sigma$, then $A^c \in \Sigma$.
- **Closed under countable unions.** If $\lbrace A_n \rbrace_{n \in \mathbb{N}}$ is a countable collection of sets of $\Sigma$, then $\bigcup_{n \in \mathbb{N}} A_n \in \Sigma$.

The class must be non-empty, because the empty class has both properties but contains no set.

For example, for a die, $\Sigma = \lbrace \emptyset, \lbrace 1, 3, 5 \rbrace, \lbrace 2, 4, 6 \rbrace, \Omega \rbrace$ is a σ-algebra on $\Omega = \lbrace 1, 2, 3, 4, 5, 6 \rbrace$. With this class we can measure the events "odd" and "even", but not the event "the result is 6".

### 4.3.2 Properties of σ-Algebras

Other important properties follow from the definition.

**$\Omega$ and $\emptyset$ are in $\Sigma$**

$$
\Omega, \emptyset \in \Sigma
$$

**Proof**

Take a set $A \in \Sigma$, which exists because $\Sigma$ is non-empty. Then $A^c \in \Sigma$, because $\Sigma$ is closed under complements. Since $\Omega = A \cup A^c$, closure under countable unions with $A_1 = A$ and $A_n = A^c$ for $n \geq 2$ gives $\Omega \in \Sigma$. Since $\emptyset = \Omega^c$, closure under complements gives $\emptyset \in \Sigma$. $\blacksquare$

**$\Sigma$ is closed under countable intersections**

If $\lbrace A_n \rbrace_{n \in \mathbb{N}}$ is a sequence of sets of $\Sigma$, then

$$
\bigcap_{n \in \mathbb{N}} A_n \in \Sigma
$$

In terms of events, $\bigcap_n A_n$ means that all the $A_n$ occur.

**Proof**

De Morgan's first law, applied to the sets $A_n^c$, gives

$$
\bigcap_{n \in \mathbb{N}} A_n = \left( \bigcup_{n \in \mathbb{N}} A_n^c \right)^c
$$

The proof of this law for a finite number of sets (see [1 Introduction to Probability and Set Theory](01-introduction-to-probability-and-set-theory.md)) also works for a countable number of sets. Each $A_n^c$ is in $\Sigma$, because $\Sigma$ is closed under complements. Then $\bigcup_n A_n^c \in \Sigma$, because $\Sigma$ is closed under countable unions, and its complement $\bigcap_n A_n$ is in $\Sigma$, because $\Sigma$ is closed under complements. $\blacksquare$

### 4.3.3 Examples of σ-Algebras

**Example 1. Power set and trivial σ-algebras**

Let $\Omega = \lbrace a, b, c \rbrace$. The **power set σ-algebra** on $\Omega$ is the class $\mathcal{P}(\Omega)$ of all the $2^3 = 8$ subsets of $\Omega$.

$$
\Sigma_1 = \lbrace \emptyset, \lbrace a \rbrace, \lbrace b \rbrace, \lbrace c \rbrace, \lbrace a, b \rbrace, \lbrace a, c \rbrace, \lbrace b, c \rbrace, \lbrace a, b, c \rbrace = \Omega \rbrace
$$

It is a σ-algebra, because the complements and the unions of subsets of $\Omega$ are also subsets of $\Omega$. It is the largest σ-algebra on $\Omega$, because every σ-algebra on $\Omega$ is a class of subsets of $\Omega$.

The **trivial σ-algebra** on $\Omega$ is

$$
\Sigma_2 = \lbrace \emptyset, \Omega \rbrace
$$

It is a σ-algebra, because $\emptyset^c = \Omega$, $\Omega^c = \emptyset$, and each union of these two sets is $\emptyset$ or $\Omega$. It is the smallest σ-algebra on $\Omega$, because every σ-algebra contains $\Omega$ and $\emptyset$.

**Example 2. Uncountable set**

Let $\Omega$ be an uncountable set, such as $\mathbb{R}$, and let

$$
C = \lbrace A \subseteq \Omega : A \text{ or } A^c \text{ is countable} \rbrace
$$

where countable means finite or countably infinite. For example, for $\Omega = \mathbb{R}$, the sets $\mathbb{Q}$ and $\mathbb{R} \setminus \lbrace 0 \rbrace$ are in $C$, but $[0, 1]$ is not, because $[0, 1]$ and its complement are both uncountable. We check whether $C$ is a σ-algebra.

- **$\Omega \in C$.** The complement $\Omega^c = \emptyset$ is countable, so $\Omega \in C$ and $C$ is non-empty.
- **Closed under complements.** Let $A \in C$. Then $A^c \in C$ if $A^c$ or $(A^c)^c = A$ is countable. Since $A \in C$, one of $A$ and $A^c$ is countable, so $A^c \in C$.
- **Closed under countable unions.** Let $\lbrace A_n \rbrace_{n \in \mathbb{N}}$ be a sequence of sets of $C$. We show that $\bigcup_n A_n \in C$.
  - If every $A_n$ is countable, then $\bigcup_n A_n$ is countable, because a countable union of countable sets is countable. So $\bigcup_n A_n \in C$.
  - If every $A_n^c$ is countable, then $\left( \bigcup_n A_n \right)^c = \bigcap_n A_n^c \subseteq A_i^c$ for any $i$. A subset of the countable set $A_i^c$ is countable, so $\bigcup_n A_n \in C$.
  - If some $A_n$ are countable and the others have a countable complement, let $I \neq \emptyset$ be the set of the indices of the countable $A_n$. Let $A_I = \bigcup_{n \in I} A_n$ and $A_{\mathbb{N} \setminus I} = \bigcup_{n \notin I} A_n$, so that $\bigcup_n A_n = A_I \cup A_{\mathbb{N} \setminus I}$. This union contains $A_{\mathbb{N} \setminus I}$, and $A \subseteq B$ implies $B^c \subseteq A^c$, so $\left( \bigcup_n A_n \right)^c \subseteq A_{\mathbb{N} \setminus I}^c$. The set $A_{\mathbb{N} \setminus I}^c = \bigcap_{n \notin I} A_n^c$ is a subset of the countable set $A_j^c$ for any $j \notin I$, so it is countable. Thus $\left( \bigcup_n A_n \right)^c$ is countable, and $\bigcup_n A_n \in C$.

$C$ is non-empty and closed under complements and countable unions, so $C$ is a σ-algebra.

### 4.3.4 σ-Algebra Generated by a Class of Sets

We often want to measure a class of sets that is not a σ-algebra, such as the class of the intervals $(a, b]$ of $\mathbb{R}$. Let $C$ be any class of subsets of a set $\Omega$. The **σ-algebra generated by $C$** is the intersection of all the σ-algebras on $\Omega$ that contain $C$.

$$
\sigma(C) = \bigcap_{C \subseteq \Sigma} \Sigma
$$

Here $C \subseteq \Sigma$ means that each set of $C$ is a set of $\Sigma$. The intersection is over at least one σ-algebra, because the power set σ-algebra $\mathcal{P}(\Omega)$ contains $C$. An intersection of σ-algebras on $\Omega$ is also a σ-algebra on $\Omega$, so $\sigma(C)$ is a σ-algebra.

$\sigma(C)$ is the **smallest** σ-algebra that contains $C$. It contains $C$, because each σ-algebra of the intersection contains $C$. If a σ-algebra $\Sigma$ contains $C$, then $\Sigma$ is one of the σ-algebras of the intersection, so $\sigma(C) \subseteq \Sigma$.

For example, for a die, let $\Omega = \lbrace 1, 2, 3, 4, 5, 6 \rbrace$ and let $C = \lbrace \lbrace 1, 3, 5 \rbrace \rbrace$, the class whose only set is the event "odd". A σ-algebra that contains $\lbrace 1, 3, 5 \rbrace$ also contains its complement $\lbrace 2, 4, 6 \rbrace$ and the sets $\Omega$ and $\emptyset$. These four sets form a σ-algebra, so

$$
\sigma(C) = \lbrace \emptyset, \lbrace 1, 3, 5 \rbrace, \lbrace 2, 4, 6 \rbrace, \Omega \rbrace
$$

### 4.3.5 Borel Sets

An important example of a σ-algebra generated by a class is the **Borel σ-algebra** on $\mathbb{R}$. Let $\Omega = \mathbb{R}$ and let $I$ be the class of all the intervals of $\mathbb{R}$, which includes the open, closed, and half-open intervals. The Borel σ-algebra on $\mathbb{R}$ is

$$
\beta(\mathbb{R}) = \sigma(I)
$$

Its sets are the **Borel sets**. Many books write $\mathcal{B}(\mathbb{R})$ in place of $\beta(\mathbb{R})$.

Some important Borel sets are the following.

- **Intervals.** The open intervals $(a, b)$, the half-open intervals $(a, b]$ and $[a, b)$, the closed intervals $[a, b]$, and the unbounded intervals, such as $(a, +\infty)$, are in $I$. Since $\sigma(I)$ contains $I$, they are Borel sets.
- **Points.** For $x \in \mathbb{R}$, the set $\lbrace x \rbrace = \bigcap_{n=1}^{\infty} \left( x - \frac{1}{n}, x + \frac{1}{n} \right)$ is a countable intersection of open intervals. A σ-algebra is closed under countable intersections, so $\lbrace x \rbrace$ is a Borel set.
- **Countable sets.** A countable set $\lbrace x_1, x_2, \dots \rbrace = \bigcup_n \lbrace x_n \rbrace$ is a countable union of the one-point sets $\lbrace x_n \rbrace$, so it is a Borel set.
- **Rational and irrational numbers.** The set $\mathbb{Q}$ of the rational numbers is countable, so $\mathbb{Q} \in \beta(\mathbb{R})$. Its complement $\mathbb{Q}^c = \mathbb{I}$, the set of the irrational numbers, is also in $\beta(\mathbb{R})$, because $\beta(\mathbb{R})$ is closed under complements.

The original definition of the Borel σ-algebra uses the open sets of $\mathbb{R}$, and it gives the same σ-algebra. Countable intersections of open intervals give all the other intervals. For example,

$$
(a, b] = \bigcap_{i \in \mathbb{N}} \left( a, b + \frac{1}{i} \right)
$$

$$
[a, b) = \bigcap_{i \in \mathbb{N}} \left( a - \frac{1}{i}, b \right)
$$

$$
[a, b] = \bigcap_{i \in \mathbb{N}} \left( a - \frac{1}{i}, b + \frac{1}{i} \right)
$$

Two sets have the same **cardinality**, or number of elements, if a bijection between them exists. The cardinality of $\beta(\mathbb{R})$ is equal to the cardinality of $\mathbb{R}$. By Cantor's theorem, a set has a smaller cardinality than its power set, so the cardinality of $\mathcal{P}(\mathbb{R})$ is larger. Thus $\beta(\mathbb{R}) \neq \mathcal{P}(\mathbb{R})$, and not every subset of $\mathbb{R}$ is a Borel set.
