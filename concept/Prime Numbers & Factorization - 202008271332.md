# Prime Numbers and Prime Factorization
 #math/numbertheory 

### Def: Prime Number
A prime number is a positive integer $p > 1$ such that $a \mid p$ implies that $a = 1$ or $a=p.$ 

- 1 is **not** a prime number - it's an identity
- 2 is the smallest and **only even** prime. 
- Every prime $>3$ is of the form(s) $6k \pm 1$ for integer $k$ (remember, $6k-1 \equiv 6k+5$). 

#### Lemma 1
If $p$ is prime and $a \in \mathbb{N}$ such that $p$ does not divide $a$, then $\gcd(a,p)=1$.

More generally, $\gcd(a,p) =1$ or $p$, depending on if $p \mid a$ or not.  

#### Lemma 2
If $p$ is prime, then $p \mid ab$ implies that $p \mid a$ or $p \mid b$. 

### Thm: Euclidean Theorem for Prime Numbers
$p>1$ is prime $\iff p \mid ab$ implies $p\mid a$ or $p \mid b$ 

#### Corollary 
If $p$ is prime and $p \mid a_1 a_2 \ldots a_n$, then $p \mid a_k, $ where $1 \leq k \leq n$.

#### Corollary
If $p, q_1, q_2, \ldots, q_n$ are all primes and $p \mid q_1 q_2 \ldots q_n$, then $p = q_k$ for some $k$, where $1 \leq k \leq n$. 

### Def: Composite Number
A positive integer $n > 1$ is composite if it's not prime. In other words, $n$ is composite if $n$ can be decomposed/written as a product of two integers: 
$$n = ab, a > 1, b < a.$$


---
## Thm: Fundamental Theorem of Arithmetic
Every positive integer $n>1$ can be expressed as a product of primes; this representation is unique, apart from the order in which the factors occur. 

### Corollary 
Any positive integer $n>1$ can be written uniquely in a *canonical form* 
$$n = p_1^{k_1} p_2^{k_2} \ldots p_r^{k_r}$$ where, for $i = 1,2, \ldots r$, each $k_i$ is a positive integer and each $p_i$ is prime, with $p_1 < p_2 < \ldots p_r.$

## Def: Alternate GCD and LCM
Given $$m =p_1^{\alpha_1} p_2^{\alpha_2} \ldots p_k^{\alpha_k}$$ and  $$n = p_1^{\beta_1} p_2^{\beta_2} \ldots p_k^{\beta_k}$$ with $\alpha_i, \beta_j \geq 0$ (if the prime doesn't appear in one of the variables, it shows up with 0.), we can define $$\gcd(m,n) = p_1^{\min\{\alpha_1, \beta_1\}} \ldots p_k^{\min\{\alpha_k, \beta_k\}}.$$

In other words, you can construct the gcd based on picking and choosing the lowest exponent of each prime. Similarly, the lcm can be written as $$lcm(m,n) = p_1^{\max\{\alpha_1, \beta_1\}} \ldots p_k^{\max\{\alpha_k, \beta_k\}}.$$

# Sieve of Eratosthenes (Primality Test)
## Thm: Bound for Prime Factor
If $n>1$ is composite, it has to have a prime factor $\leq \sqrt{n}$. 

The contrapositive statement is that if $n$ is not divisible by any prime $\leq \sqrt{n}$, then $n$ has to be prime. 

> Ex: Determine if 257 is prime. Starting out, $\sqrt{257} \approx 16$. Primes less than 16 are the following: $$2,3,5,7,11,13.$$ Testing all of these, none are divisible. Thus, 257 is prime. $\checkmark$ 
> </n>
>  Note: To test if it's a multiple of 7, we can rewrite $257 = 210 + 49 - 2$. We can't write 257 as a sum/difference of multiples of 7. 

## Def: Fermat Primes
Fermat primes are primes in the form $2^m + 1$. 

Notice that $m$ cannot have an odd factor $>1$. If $m=kq$ where $k>1$ is odd, then we can write$2^{kq}+1 = (2^q)^k + 1$ which can be generalized as a sum of cubes (i.e. factorable). 

In other words, $m = 2^n$ for some $n$. 

Fermat conjectured the sequence $F_n = 2^{2^n}+1$. Sadly, Euler shows that this breaks at $F_5 = 2^{32}+1$, as 641 divides it. Oof. In fact, no other Fermat primes have been found. :( 

## Def: Mersenne Primes
These primes are of the form $2^p - 1$. 

So, if $2^m-1$ is a prime, then $m$ must be prime. If $m$ is composite, i.e. $=ab, a,b > 1$, then $2^m - 1 = 2^{a^b} -1 = (2^a-1)(2^a^{b-1} + \ldots 2^a + 1).$ Since it'd be factorable, $m$ needs to not be composite. 

Strangely, the fifth number in this sequence isn't actually prime, just like Fermat Primes. Oof. There are some other ones, however, so not a blunder. For example $2^(77,232,917) - 1$ is prime.

#  Thm: Infinitude of Primes
There are infinitely many primes. 

> Proof: Assume not, i.e. $p_1, p_2, \ldots, p_n$ are all the primes. Then, we need to construct a number that cannot be divisible by any of these. Define $$N = p_1p_2\ldots p_n + 1.$$ If $p_i \mid N,$ that implies that $p_i \mid 1$. $N>1$, so by the Fundamental Theorem of Arithmetic, $N$ has a prime factor $q$ that is different from the above set of primes. We have our contradiction!

### Corollary
$$q \mid p_1p_2\ldots p_n + 1 , \text{   so   } p_{n+1} \leq p_1p_2\ldots p_n + 1.$$

This is a **very rough** upper bound. 

> However, Bertrand found that for any $n>1$, then exists at least one prime between $n$ and $2n$.

### Corollary
$$p_n \leq 2^n.$$ 

#idea Bahattin has a friend who researches math history. 

### Corollary

$1+\frac{1}{2}+\frac{1}{3} + \ldots \frac{1}{n}$ is not an integer when $n \geq 2.$

# Thm: Dirichlet's Result
If $a,b \in \mathbb{Z}_{+}$ such that $\gcd(a,b)=1$, then the sequence $\{ ak+b \mid k\in \mathbb{Z}\}$ contains infinitely many primes. 

This can be applied via examples like "We know that there are infinitely many primes that end in $999$." This is because every number that ends in 999 is of the form $1000k + 999$ and $(1000,999) = 1$. 

### Corollary 
For any $n \geq 2$ we can find $n$ consecutive composite numbers $$(n+1)!+2, (n+1)!+3, \ldots, (n+1)!+(n+1).$$

# Thm: No Arithmetic Progression
Let $a,b \in \mathbb{Z}_{+}$ . There is no arithmetic progression $a, a+b, a+2b, \ldots$ whose terms are all primes. 
 
---
# Related:
[[Divisibility Theorems in the Integers - 202008271248]]
[[Number Theory Prelims - 202008271247]]

# Sources:
Burton, David M. â€œELEMENTARY NUMBER THEORY,â€ n.d., 452.
