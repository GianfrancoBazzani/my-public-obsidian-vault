# Introduction

Deductive reasoning in mathematics is usually presented in the form of a proof.

An integer larger than 1 is **prime** if it cannot be written as a product of two smaller positive integers. If an integer can be written as a product of two smaller positive integers, then it is **composite**.

> [!note] Conjecture 2
> Suppose $n$ is an integer larger than 1 and $n$ is not prime. Then $2^n - 1$ is not prime.

**Proof.** Since $n$ is not prime, there are positive integers $a$ and $b$ such that $a < n$, $b < n$, and $n = ab$.

Let $x = 2^b - 1$ and $y = 1 + 2^b + 2^{2b} + \cdots + 2^{(a-1)b}$. Then:

$$
\begin{aligned}
xy &= (2^b - 1)\left(1 + 2^b + 2^{2b} + \cdots + 2^{(a-1)b}\right) \\
   &= 2^b\left(1 + 2^b + 2^{2b} + \cdots + 2^{(a-1)b}\right) - \left(1 + 2^b + 2^{2b} + \cdots + 2^{(a-1)b}\right) \\
   &= \left(2^b + 2^{2b} + \cdots + 2^{ab}\right) - \left(1 + 2^b + 2^{2b} + \cdots + 2^{(a-1)b}\right) \\
   &= 2^{ab} - 1 \\
   &= 2^n - 1
\end{aligned}
$$

Since $b < n$, we have $x = 2^b - 1 < 2^n - 1$. Also, since $ab = n > a$, it follows that $b > 1$, so $x = 2^b - 1 > 1$. Therefore $2^n - 1$ is a product of two smaller positive integers, so $2^n - 1$ is not prime.

Conjecture 2 is therefore a theorem.