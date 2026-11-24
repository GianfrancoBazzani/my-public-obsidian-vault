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

## 4.4 The Probability Measure

When $\Omega$ is countable, we can give a probability to every set of $\mathcal{P}(\Omega)$. For example, for a fair die, each set $A \subseteq \Omega$ has the probability $P(A) = \frac{\text{number of elements of } A}{6}$.

When $\Omega$ is uncountable, such as $\mathbb{R}$, problems start, because no function gives a consistent value to every subset of $\mathbb{R}$. Thus we measure only the sets of a σ-algebra, and in particular of the Borel σ-algebra $\beta(\mathbb{R})$. A σ-algebra is closed under the usual set operations, finite or countable, such as complements, unions, and intersections. Thus these operations on sets that we can measure give sets that we can measure.

### 4.4.1 Measurable Space

A **measurable space** is a pair $(\Omega, \Sigma)$, where $\Sigma$ is a σ-algebra on $\Omega$. If $\Sigma$ is a σ-algebra of events, the pair is also a **probabilizable space**, because we can give it a probability. A measurable space has no measure yet. When we add a probability measure $P$, we get the probability space $(\Omega, \Sigma, P)$.

For example, $(\mathbb{R}, \beta(\mathbb{R}))$ is a measurable space, and so is $(\Omega, \mathcal{P}(\Omega))$ for a die.

### 4.4.2 Kolmogorov Axioms

After the class of sets on which we can give probabilities, the last element is the tool that gives them, which is the probability measure.

Let $(\Omega, \Sigma)$ be a measurable space. A **probability measure** is a function $P : \Sigma \to [0, 1]$ with three properties.

1. **Non-negativity.** $P(A) \geq 0$ for all $A \in \Sigma$.
2. **σ-additivity.** If $\lbrace A_n \rbrace_{n \in \mathbb{N}} \subseteq \Sigma$ are pairwise disjoint, that is, $A_i \cap A_j = \emptyset$ for $i \neq j$, then

$$
P\left(\bigcup_{n \in \mathbb{N}} A_n\right) = \sum_{n \in \mathbb{N}} P(A_n)
$$

3. **Normalization.** $P(\Omega) = 1$.

These are the axioms of Kolmogorov (see [1 Introduction to Probability and Set Theory](01-introduction-to-probability-and-set-theory.md)), with the σ-algebra $\Sigma$ as the class of events. σ-additivity is the countable additivity of the length $\lambda$, and $P(\Omega) = 1$ makes the total probability equal to $1$.

### 4.4.3 Probability Space

A **probability space** is a triple $(\Omega, \Sigma, P)$, where $(\Omega, \Sigma)$ is a measurable space and $P$ is a probability measure on $\Sigma$. For $A \in \Sigma$, $P(A)$ is the probability of the event $A$.

For example, for a fair die, $(\Omega, \mathcal{P}(\Omega), P)$ with $\Omega = \lbrace 1, 2, 3, 4, 5, 6 \rbrace$ and $P(A) = \frac{\text{number of elements of } A}{6}$ is a probability space. The event "odd" has the probability $P(\lbrace 1, 3, 5 \rbrace) = \frac{3}{6} = \frac{1}{2}$.

Two properties follow from the axioms. Let $(\Omega, \Sigma, P)$ be a probability space and let $A, B \in \Sigma$.

**Probability of a difference**

$$
P(A \setminus B) = P(A) - P(A \cap B)
$$

In particular, if $B \subseteq A$, then $A \cap B = B$ and

$$
P(A \setminus B) = P(A) - P(B)
$$

**Proof**

First, $P(\emptyset) = 0$. The sets $A_n = \emptyset$ are pairwise disjoint, so σ-additivity gives $P(\emptyset) = \sum_{n} P(\emptyset)$, and this sum is finite only if $P(\emptyset) = 0$.

The sets $A \setminus B$ and $A \cap B$ are disjoint, and their union is $A$. σ-additivity with $A_1 = A \setminus B$, $A_2 = A \cap B$, and $A_n = \emptyset$ for $n \geq 3$ gives

$$
P(A) = P(A \setminus B) + P(A \cap B)
$$

We subtract $P(A \cap B)$ from both sides. $\blacksquare$

**Probability of the complement**

$$
P(A^c) = 1 - P(A)
$$

**Proof**

The sets $A$ and $A^c$ are disjoint, and their union is $\Omega$. σ-additivity with $A_1 = A$, $A_2 = A^c$, and $A_n = \emptyset$ for $n \geq 3$, together with $P(\emptyset) = 0$ and $P(\Omega) = 1$, gives

$$
1 = P(\Omega) = P(A) + P(A^c)
$$

We subtract $P(A)$ from both sides. $\blacksquare$

### 4.4.4 Inclusion-Exclusion Principle

Let $(\Omega, \Sigma, P)$ be a probability space and let $A_1, A_2, \dots, A_n \in \Sigma$. For two events,

$$
P(A_1 \cup A_2) = P(A_1) + P(A_2) - P(A_1 \cap A_2)
$$

The sum $P(A_1) + P(A_2)$ counts the intersection $A_1 \cap A_2$ two times, so the formula subtracts it one time. For $n$ events, the **inclusion-exclusion principle** is

$$
\begin{aligned}
P\left(\bigcup_{i=1}^{n} A_i\right) = & \sum_{i=1}^{n} P(A_i) - \sum_{1 \leq i < j \leq n} P(A_i \cap A_j) \\
& + \sum_{1 \leq i < j < k \leq n} P(A_i \cap A_j \cap A_k) - \dots + (-1)^{n-1} P\left(\bigcap_{i=1}^{n} A_i\right)
\end{aligned}
$$

It is the same formula as the inclusion-exclusion principle for the number of elements of a union (see [3 Combinatorics](03-combinatorics.md)), with probabilities in place of numbers of elements.

For example, for a fair die, let $A_1 = \lbrace 1, 3, 5 \rbrace$ be the event "odd" and $A_2 = \lbrace 4, 5, 6 \rbrace$ the event "greater than 3". Then $A_1 \cap A_2 = \lbrace 5 \rbrace$ and

$$
P(A_1 \cup A_2) = \frac{1}{2} + \frac{1}{2} - \frac{1}{6} = \frac{5}{6}
$$

which is the probability of $A_1 \cup A_2 = \lbrace 1, 3, 4, 5, 6 \rbrace$.

### 4.4.5 Continuity of the Probability Measure

Let $(\Omega, \Sigma, P)$ be a probability space and let $\lbrace A_n \rbrace_{n \in \mathbb{N}}$ be a sequence of events of $\Sigma$, with the limits of sequences of sets (see [2 Sequences of Sets](02-sequences-of-sets.md)).

**Monotone sequences**

If $\lbrace A_n \rbrace$ is increasing or decreasing, then

$$
P\left(\lim_{n \to \infty} A_n\right) = \lim_{n \to \infty} P(A_n)
$$

This is the continuity of the length $\lambda$ for increasing sequences, now for probabilities and also for decreasing sequences.

**General sequences**

For any sequence,

$$
P\left(\liminf_{n \to \infty} A_n\right) \leq \liminf_{n \to \infty} P(A_n) \leq \limsup_{n \to \infty} P(A_n) \leq P\left(\limsup_{n \to \infty} A_n\right)
$$

Thus, if $\lbrace A_n \rbrace$ converges, then the two outer terms are equal, and $P(\lim A_n) = \lim P(A_n)$.


### 4.4.6 Characterization of σ-Additivity

Let $(\Omega, \Sigma)$ be a measurable space and let $P : \Sigma \to \mathbb{R}^+$ be a **finitely additive** measure, that is, $P(A \cup B) = P(A) + P(B)$ for disjoint $A, B \in \Sigma$. Each of the two continuity properties below makes $P$ σ-additive.

1. **Continuity for increasing sequences.** If $P(A) = \lim_{n \to \infty} P(A_n)$ for every increasing sequence $\lbrace A_n \rbrace_{n \in \mathbb{N}} \subseteq \Sigma$ with $A = \bigcup_{n \in \mathbb{N}} A_n$, then $P$ is σ-additive.
2. **Continuity at the empty set.** If $\lim_{n \to \infty} P(A_n) = 0$ for every decreasing sequence $\lbrace A_n \rbrace_{n \in \mathbb{N}} \subseteq \Sigma$ with $\bigcap_{n \in \mathbb{N}} A_n = \emptyset$, then $P$ is σ-additive.

**Proof**

Let $\lbrace A_n \rbrace_{n \in \mathbb{N}} \subseteq \Sigma$ be pairwise disjoint and let $A = \bigcup_{n=1}^{\infty} A_n$. We must show that $P(A) = \sum_{n=1}^{\infty} P(A_n)$.

1. The finite unions $\bigcup_{n=1}^{m} A_n$ increase to $A$. Continuity, and then finite additivity, give

$$
P(A) = \lim_{m \to \infty} P\left(\bigcup_{n=1}^{m} A_n\right) = \lim_{m \to \infty} \sum_{n=1}^{m} P(A_n) = \sum_{n=1}^{\infty} P(A_n)
$$

Continuity changes the probability of the limit $A$ into the limit of the probabilities of the finite unions. Each finite union is a union of disjoint sets, so finite additivity writes its probability as the finite sum $\sum_{n=1}^{m} P(A_n)$. The limit of these finite sums is, by definition, the infinite sum.

2. The sets $A \setminus \bigcup_{n=1}^{m} A_n$ decrease to $\emptyset$. $A$ is the disjoint union of $\bigcup_{n=1}^{m} A_n$ and this set, so finite additivity and continuity at the empty set give

$$
0 = \lim_{m \to \infty} P\left(A \setminus \bigcup_{n=1}^{m} A_n\right) = \lim_{m \to \infty} \left(P(A) - \sum_{n=1}^{m} P(A_n)\right) = P(A) - \sum_{n=1}^{\infty} P(A_n)
$$

Finite additivity writes $P\left(A \setminus \bigcup_{n=1}^{m} A_n\right)$ as $P(A)$ minus the finite sum $\sum_{n=1}^{m} P(A_n)$. The limit of these finite sums is the infinite sum, and this limit exists because the limit of the left side is $0$.

$\blacksquare$

Thus σ-additivity is finite additivity together with continuity. The length $\lambda$ has the same property, where additivity and continuity for increasing sequences together give countable additivity.

**Alternative characterization**

A finitely additive measure $P : \Sigma \to \mathbb{R}^+$ is σ-additive if and only if, for every sequence $\lbrace A_n \rbrace_{n \in \mathbb{N}} \subseteq \Sigma$,

$$
P\left(\bigcup_{n \in \mathbb{N}} A_n\right) \leq \sum_{n=1}^{\infty} P(A_n)
$$

This inequality is **σ-subadditivity**. The sets $A_n$ do not have to be disjoint, and the sum can be larger than the probability of the union, because it counts the overlaps more than one time.

## 4.5 Borel-Cantelli Lemmas

The **Borel-Cantelli lemmas** answer one main question. What is the probability of the superior limit of a sequence of events $\lbrace A_n \rbrace_{n \in \mathbb{N}}$?

$$
\limsup_{n \to \infty} A_n = \bigcap_{k=1}^{\infty} \bigcup_{n=k}^{\infty} A_n
$$

By the definition of the superior limit (see [2 Sequences of Sets](02-sequences-of-sets.md)), an outcome is in $\limsup A_n$ if and only if it is in infinitely many $A_n$. Thus $P(\limsup A_n)$ is the probability that the events $A_n$ occur again and again, that is, infinitely many times. For example, if $A_n$ is the event "toss $n$ of a coin gives heads", then $\limsup A_n$ is the event "infinitely many tosses give heads".

### 4.5.1 First Borel-Cantelli Lemma

Let $\lbrace A_n \rbrace_{n \in \mathbb{N}}$ be a sequence of events in a probability space $(\Omega, \Sigma, P)$. If

$$
\sum_{n=1}^{\infty} P(A_n) < \infty
$$

then

$$
P\left(\limsup_{n \to \infty} A_n\right) = 0
$$

If the probabilities of the events have a finite sum, then with probability $1$ only finitely many of the events occur. The lemma does not need independent events.

For example, let $A_n$ be the event "the first $n$ tosses of a fair coin give heads". Then $\sum_{n=1}^{\infty} P(A_n) = \sum_{n=1}^{\infty} \left(\frac{1}{2}\right)^n = 1 < \infty$, so $P(\limsup A_n) = 0$. Here $\limsup A_n$ is the event "all the tosses give heads".

### 4.5.2 Second Borel-Cantelli Lemma

If the events $A_n$ are independent and

$$
\sum_{n=1}^{\infty} P(A_n) = \infty
$$

then

$$
P\left(\limsup_{n \to \infty} A_n\right) = 1
$$

If the events are independent and the probabilities have an infinite sum, then with probability $1$ infinitely many of the events occur. Without independence, this lemma is not always true.

For example, let $A_n$ be the event "toss $n$ of a fair coin gives heads". The tosses are independent and $\sum_{n=1}^{\infty} P(A_n) = \sum_{n=1}^{\infty} \frac{1}{2} = \infty$, so infinitely many tosses give heads with probability $1$.
