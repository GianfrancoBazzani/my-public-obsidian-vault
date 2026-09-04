# Introduction

Deductive reasoning in mathematics is usually presented in the form of a proof.

## Prime Numbers

An integer larger than 1 is **prime** if it cannot be written as a product of two smaller positive integers. If an integer can be written as a product of two smaller positive integers, then it is **composite**.

> [!note] Conjecture 1
> Suppose $n$ is an integer larger than 1 and $n$ is prime. Then $2^n - 1$ is prime.

Conjecture 1 is false. To disprove it, we use a counterexample.

A **counterexample** is one case that satisfies the hypothesis but does not satisfy the conclusion. A conjecture of this form claims that no exception exists. Therefore one counterexample is sufficient to disprove the whole conjecture. To prove such a conjecture, you must examine every case. To disprove it, you only need one case.

Test the prime exponents in order:

| $n$ | $2^n - 1$ | Result |
| --- | --- | --- |
| 2 | 3 | prime |
| 3 | 7 | prime |
| 5 | 31 | prime |
| 7 | 127 | prime |
| 11 | 2047 | **not prime** |

The exponent $n = 11$ is the smallest counterexample:

$$2^{11} - 1 = 2047 = 23 \cdot 89$$

The number 11 satisfies the hypothesis, because 11 is prime. The number 2047 does not satisfy the conclusion, because 2047 has the divisors 23 and 89. Therefore Conjecture 1 is false.

> [!warning] The first four rows agree with the conjecture, but four cases are not a proof. Examples suggest a conjecture. Examples never prove a conjecture.

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

> [!note] Theorem 3 (Euclid)
> There are infinitely many prime numbers.
>
> Source: Euclid, *Elements*, Book IX, Proposition 20 (c. 300 BC). 

**Proof.** Suppose there are only finitely many prime numbers.

Let $p_1, p_2, \ldots, p_n$ be a list of all prime numbers.

Let $m = p_1 p_2 \cdots p_n + 1$.

Note that $m$ is not divisible by any prime $p_i$ in the list. If you divide $m$ by $p_i$, the quotient is the product of the other primes in the list, and the remainder is 1.

Every integer larger than 1 is either a prime or a composite number. A composite number is a product of two or more primes.

Since $m > 1$, the number $m$ is either a prime or a product of two or more primes.

Suppose that $m$ is prime. Then $m$ is a prime that is not in the list, because no prime of the list divides $m$. This contradicts the assumption that the list contains all the prime numbers. 

Now suppose that $m$ is composite. Then some prime $q$ divides $m$. No prime of the list divides $m$, so $q$ is not in the list. This contradicts the assumption again.

The assumption that there are finitely many prime numbers gives a contradiction in both cases. Therefore there are infinitely many prime numbers.

## Mersenne Primes

A prime of the form $2^n - 1$ is a **Mersenne prime**.

Conjecture 2 (now a theorem) shows that $2^n - 1$ is not prime when $n$ is not prime. 

The counterexample to Conjecture 1 shows that if $n$ is prime, then $2^n - 1$ can be prime or composite.

Theorem 3 gives infinitely many prime exponents, so there are infinitely many candidates. Nonetheless, this does not prove that the quantity of Mersenne primes is infinite. Although many Mersenne prime numbers have been found, it is still not known if there are infinitely many of them.

## Perfect Numbers

A positive integer $n$ is **perfect** if $n$ is equal to the sum of all positive integers smaller than $n$ that divide $n$.

The smallest perfect number is 6. The positive integers smaller than 6 that divide 6 are 1, 2 and 3:

$$1 + 2 + 3 = 6$$

The next perfect number is 28. Its divisors are 1, 2, 4, 7 and 14:

$$1 + 2 + 4 + 7 + 14 = 28$$

Euclid proved that if $2^n-1$ is prime, then $2^{n-1}(2^n-1)$ is perfect. Thus, every Mersenne prime gives rise to a perfect number.

Euler (1707-1783) proved that every even perfect number arises in this way.

Because it is not known if there are infinitely many Mersenne primes, it is not known if there are infinitely many even perfect numbers.


> [!note] Theorem 4
> For every positive integer $n$, there is a sequence of $n$ consecutive positive integers that contains no primes.

**Proof.** Suppose $n$ is a positive integer.

Let $x = (n+1)! + 2$.

Consider the list $x, x+1, x+2, \ldots, x+(n-1)$.

Note that:

$$
\begin{aligned}
x &= 1 \cdot 2 \cdot 3 \cdots (n+1) + 2 \\
  &= 2\left(1 \cdot 3 \cdot 4 \cdots (n+1) + 1\right)
\end{aligned}
$$

Thus $x$ is composite, because $x$ is a product of two smaller positive integers.

Similarly:

$$
\begin{aligned}
x + 1 &= 1 \cdot 2 \cdot 3 \cdots (n+1) + 3 \\
      &= 3\left(1 \cdot 2 \cdot 4 \cdots (n+1) + 1\right)
\end{aligned}
$$

Consider any $x+i$ where $0 \leq i \leq n-1$. Then:

$$
\begin{aligned}
x + i &= 1 \cdot 2 \cdot 3 \cdots (n+1) + (2 + i) \\
\end{aligned}
$$

Since $0 \leq i \leq n-1$, we have $2 \leq i + 2 \leq n + 1$. Therefore $i + 2$ is one of the factors of $(n+1)!$, and $x + i$ can be written as a product of two integers:

$$
\begin{aligned}
x + i &= (i + 2)\left(\frac{(n+1)!}{i+2} + 1\right)
\end{aligned}
$$

Note that the quotient $\frac{(n+1)!}{i+2}$ is an integer, because $i + 2$ is a factor of $(n+1)!$.

Both factors are larger than 1, because $i + 2 \geq 2$ and $\frac{(n+1)!}{i+2} + 1 \geq 2$. Thus both factors are smaller than $x + i$, so $x + i$ is composite.

Therefore the list $x, x+1, \ldots, x+(n-1)$ contains $n$ consecutive positive integers and none of them is prime.

## Twin Primes

Two prime numbers that differ by 2 are **twin primes**.

Examples: $(3, 5)$, $(5, 7)$, $(11, 13)$, $(29, 31)$.

> [!note] Twin Primes Conjecture
> There are infinitely many pairs of twin primes.

This conjecture is not proved and not disproved. It is one of the famous open problems in number theory.

## Exercises

6) The sequence 3, 5, 7 is a list of three prime numbers such that each pair of adjacent numbers in the list differ by two. Are there any more such "triplet primes"?

> [!note] Triplet Primes Conjecture
> The sequence $3, 5, 7$ is the only sequence of three primes in which each pair of adjacent numbers differs by two.

**Proof.** Consider a sequence $n$, $n+2$, $n+4$ where the three numbers are prime.

First, examine the small cases. If $n = 1$ or $n = 2$, the sequence contains a number that is not prime (1 or 4). If $n = 3$, the sequence is $3, 5, 7$, and all three numbers are prime.

Now suppose $n > 3$. Divide $n$ by 3 to get $n = 3q + r$, where $r \in \{0, 1, 2\}$.

- If $r = 0$, then $n = 3q$, so 3 divides $n$.
- If $r = 1$, then $n + 2 = 3q + 3 = 3(q + 1)$, so 3 divides $n + 2$.
- If $r = 2$, then $n + 4 = 3q + 6 = 3(q + 2)$, so 3 divides $n + 4$.

In each case, one number of the sequence is a multiple of 3. Since $n > 3$, that number is larger than 3, so it is a product of 3 and a smaller integer larger than 1. Thus that number is composite, and the sequence does not contain three primes.

Therefore $3, 5, 7$ is the only triplet of primes, and the conjecture is a theorem.
