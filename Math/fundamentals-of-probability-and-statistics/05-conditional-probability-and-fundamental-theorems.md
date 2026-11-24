# 5 Conditional Probability and Fundamental Theorems

## 5.1 Conditional Probability

If we know that an event $B$ occurred, then we also know that $B^c$ did not occur. Thus the probability of an event $A$ depends only on the outcomes of $A$ that are in $B$, which are the outcomes of $A \cap B$.

The information of the system, which was in the σ-algebra $\Sigma$, is now in the class

$$
\Sigma_B = \lbrace A \cap B : A \in \Sigma \rbrace
$$

$\Sigma_B$ is the **σ-algebra restricted to $B$**. It is a σ-algebra on $B$, because $B$ takes the role of $\Omega$.

Thus, with conditional probability, we change the probability space.

$$
(\Omega, \Sigma, P) \to (B, \Sigma_B, P_B)
$$

Here $P(B) > 0$, and for each $C = A \cap B$ with $A \in \Sigma$,

$$
P_B(C) = \frac{P(C)}{P(B)} = \frac{P(A \cap B)}{P(B)}
$$

The division by $P(B)$ makes $P_B(B) = 1$, so $P_B$ is a probability measure on $\Sigma_B$. $B$ is the new sample space.

The **conditional probability** of $A$ given $B$ is the probability of $A$ when we know that $B$ occurred. We write it $P(A \mid B)$.

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

Thus $P(A \mid B) = P_B(A \cap B)$.

For example, we roll a fair die, and we know that the result is even, that is, $B = \lbrace 2, 4, 6 \rbrace$ occurred. What is the probability that the result is at most $3$, that is, $A = \lbrace 1, 2, 3 \rbrace$?

- **Before we know $B$.** The sample space is $\Omega = \lbrace 1, 2, 3, 4, 5, 6 \rbrace$, each result has the probability $\frac{1}{6}$, and $P(A) = \frac{3}{6} = \frac{1}{2}$.
- **After we know $B$.** The results $1$, $3$, and $5$ are no longer possible, so the new sample space is $B$. The part of $A$ that is still possible is $A \cap B = \lbrace 2 \rbrace$.
- **The new probability.** $P(B) = \frac{3}{6} = \frac{1}{2}$ and $P(A \cap B) = \frac{1}{6}$, so

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{1/6}{1/2} = \frac{1}{3}
$$

## 5.2 Independent Events

Two events $A$ and $B$ are **independent** if the occurrence of $A$ does not change the probability of $B$, and the occurrence of $B$ does not change the probability of $A$. If $P(A) > 0$ and $P(B) > 0$, this means that

$$
P(A \mid B) = P(A) \qquad \text{and} \qquad P(B \mid A) = P(B)
$$

The formula of the conditional probability gives

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)} \iff P(A) = \frac{P(A \cap B)}{P(B)}
$$

so

$$
\boxed{P(A \cap B) = P(A \mid B) \cdot P(B) = P(A) \cdot P(B)}
$$

Thus two events are independent if the probability of their intersection is the product of their probabilities.

> [!NOTE]
> **Independence and the joint distribution**
>
> Independence is a much stronger property than zero correlation. Whether two random variables $X$ and $Y$ are independent depends on their joint distribution and its parameters, more than on the nature of the random phenomenon. To check it, we look at whether the joint distribution is the product of the marginal distributions, which is the same product rule as for the probability of an intersection.
>
> $$
> F_{X,Y}(x, y) = F_X(x) \cdot F_Y(y)
> $$
>
> This question is essential in stochastic processes, where we study the joint distributions of the variables of the process.

For example, for a fair die, let $A = \lbrace 2, 4, 6 \rbrace$ be the event "even" and $B = \lbrace 1, 2 \rbrace$ the event "at most 2". Then $A \cap B = \lbrace 2 \rbrace$ and

$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{1/6}{2/6} = \frac{1}{2} = P(A)
$$

Thus the information "the result is at most 2" does not change the probability of "even", and $A$ and $B$ are independent. In the die example of conditional probability, the events "at most 3" and "even" are not independent, because $P(\lbrace 1, 2, 3 \rbrace \mid \lbrace 2, 4, 6 \rbrace) = \frac{1}{3}$, but $P(\lbrace 1, 2, 3 \rbrace) = \frac{1}{2}$.

## 5.3 Fundamental Theorems of Probability

### 5.3.1 Law of Total Probability

Let $B_1, \dots, B_n$ be a **partition** of $\Omega$, that is, $B_i \cap B_j = \emptyset$ for $i \neq j$ and $\bigcup_{i=1}^{n} B_i = \Omega$, with $P(B_i) > 0$ for each $i$. Then, for each event $A$,

$$
P(A) = \sum_{i=1}^{n} P(A \cap B_i) = \sum_{i=1}^{n} P(A \mid B_i) P(B_i)
$$

The sets $A \cap B_i$ are disjoint and their union is $A$, so additivity gives the first equality. The formula of the conditional probability gives $P(A \cap B_i) = P(A \mid B_i) P(B_i)$, which is the second equality. Thus we can find the probability of $A$ from its probabilities in each case $B_i$.

For example, for a fair die, let $B_1 = \lbrace 2, 4, 6 \rbrace$ ("even") and $B_2 = \lbrace 1, 3, 5 \rbrace$ ("odd"), and let $A = \lbrace 1, 2, 3 \rbrace$ ("at most 3"). Then $P(A \mid B_1) = \frac{1}{3}$ and $P(A \mid B_2) = \frac{2}{3}$, so

$$
P(A) = \frac{1}{3} \cdot \frac{1}{2} + \frac{2}{3} \cdot \frac{1}{2} = \frac{1}{2}
$$

**Monty Hall paradox**

In a game show, there are three doors. A car is behind one door, and a goat is behind each of the other two doors. The player chooses a door. Then the host, who knows where the car is, opens one of the other two doors and shows a goat. The host then lets the player change to the last closed door. Should the player change?

- **If the player does not change.** The player wins only if the first door has the car, so $P(\text{win}) = \frac{1}{3}$.
- **If the player changes.** The events "the first door has the car" and "the first door has a goat" are a partition of $\Omega$. If the first door has the car, the player changes to a goat. If the first door has a goat, the host shows the other goat, so the player changes to the car. The law of total probability gives

$$
\begin{aligned}
P(\text{win}) = & \ P(\text{win} \mid \text{car first}) \cdot P(\text{car first}) + P(\text{win} \mid \text{goat first}) \cdot P(\text{goat first}) \\
= & \ 0 \cdot \frac{1}{3} + 1 \cdot \frac{2}{3} = \frac{2}{3}
\end{aligned}
$$

Thus the player should change the door, because the probability to win is two times larger.

**Brain teaser. Increasing order with dice**

We roll a fair die three times. What is the probability that the three numbers are in increasing order? Let $A$ be the event "the three numbers are in increasing order".

The numbers can be in increasing order only if they are all different. Thus we use the partition "three different numbers" and "not three different numbers", and the law of total probability gives

$$
\begin{aligned}
P(A) = & \ P(A \mid \text{three different}) \cdot P(\text{three different}) \\
& + P(A \mid \text{not three different}) \cdot P(\text{not three different})
\end{aligned}
$$

- **Three different numbers.** The first roll can be any number, the second roll must be different from the first, and the third roll must be different from the other two. Thus $P(\text{three different}) = 1 \cdot \frac{5}{6} \cdot \frac{4}{6} = \frac{5}{9}$.
- **Increasing order.** Three different numbers have $3! = 6$ orders with the same probability, and only one of them is increasing. Thus $P(A \mid \text{three different}) = \frac{1}{6}$.
- **Not three different numbers.** Two equal numbers cannot be in increasing order, so $P(A \mid \text{not three different}) = 0$.

Thus

$$
P(A) = \frac{1}{6} \cdot \frac{5}{9} + 0 = \frac{5}{54}
$$

### 5.3.2 Product Rule

Let $A_1, A_2, \dots, A_n$ be events of a probability space $(\Omega, \Sigma, P)$ with $P\left(\bigcap_{i=1}^{n-1} A_i\right) > 0$. Then

$$
P(A_1 \cap A_2 \cap \dots \cap A_n) = P(A_1) \cdot P(A_2 \mid A_1) \cdot P(A_3 \mid A_1 \cap A_2) \cdots P(A_n \mid A_1 \cap A_2 \cap \dots \cap A_{n-1})
$$

The rule applies $P(A \cap B) = P(A \mid B) \cdot P(B)$ again and again. Each factor is the probability of the next event, given that all the events before it occurred. The condition $P\left(\bigcap_{i=1}^{n-1} A_i\right) > 0$ makes each conditional probability defined, because each intersection $A_1 \cap \dots \cap A_k$ with $k \leq n - 1$ contains $\bigcap_{i=1}^{n-1} A_i$.

For example, we draw three cards from a deck of 52 cards, without replacement. Let $A_i$ be the event "card $i$ is an ace". Then

$$
P(A_1 \cap A_2 \cap A_3) = \frac{4}{52} \cdot \frac{3}{51} \cdot \frac{2}{50} = \frac{1}{5525}
$$

### 5.3.3 Bayes' Theorem

Let $A_1, A_2, \dots, A_n$ be a partition of $\Omega$ with $P(A_j) > 0$ for each $j$, and let $A$ and $B$ be events of $(\Omega, \Sigma, P)$ with $P(A) > 0$ and $P(B) > 0$. Then

$$
P(A \mid B) = \frac{P(A) P(B \mid A)}{P(B)} = \frac{P(A) P(B \mid A)}{\sum_{j=1}^{n} P(B \mid A_j) P(A_j)}
$$

The first equality follows from $P(A \cap B) = P(A \mid B) P(B) = P(B \mid A) P(A)$. In the second equality, the law of total probability gives the denominator $P(B)$. Usually $A$ is one of the sets $A_i$ of the partition.

Bayes' theorem reverses the direction of the condition. It gives $P(A \mid B)$ from $P(B \mid A)$. $P(A)$ is the **prior probability**, and $P(A \mid B)$ is the **posterior probability**, which is the probability of $A$ after the new information $B$.

For example, $1\%$ of a population has a disease $D$. A test is positive ($+$) for $99\%$ of the sick people and for $5\%$ of the healthy people. The events $D$ and $D^c$ are a partition, so

$$
P(D \mid +) = \frac{P(D) P(+ \mid D)}{P(+ \mid D) P(D) + P(+ \mid D^c) P(D^c)} = \frac{0.01 \cdot 0.99}{0.99 \cdot 0.01 + 0.05 \cdot 0.99} = \frac{1}{6}
$$

Thus, after a positive test, the probability of the disease changes from the prior $1\%$ to the posterior $\frac{1}{6} \approx 17\%$.
