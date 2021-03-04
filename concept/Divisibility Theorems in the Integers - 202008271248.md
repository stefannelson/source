# Divisibility Theorems
#math/numbertheory

### Thm 2.1: Division Algorithm
Given integers $a, b$ with $b> 0$, there exists unique integers $q,r$ satisfying 
$$a = qb + r$$  
where $0 \leq r < b$.

#### Corollary 
If $a, b \in \mathbb{Z}$ with $b \neq 0$, then there exist unique integers $q,r$ such that $$a = qb+r, \qquad 0 \leq r < |b|$$ 

The main difference here is that b can be negative in this case, but the requirement for the corollary to take effect is nearly the same. 

Additionally, if $b>0$, then the possible remainders we get when we divide a number by $b$ are $1,2,\ldots,b-1$. 

From here, Every integer can be written in the following forms:
1. $2k, 2k+1$
2. $3k, 3k+1, 3k+2$
3. $4k, 4k+1, 4k+2, 4k+3$
4. etc. 

For any integer $m,  m^2$ is of the form $3k, 3k+1$.
- $(3k)^2 = 9k^2, (3k \pm 1)^2 = 9k^2 \pm 6k+1 = 3(3k^2 \pm 2k)+1.$

If $m$ is odd, then $m^2$ is of the form $8k+1$.
- $m$ odd implies that $m=2n+1$, so $m^2 = 4n(n+1)+1$.
- When you have two consecutive integers, one has to be even. 
- $= 4 \cdot 2k+1 = 8k+1$.

$m^2$ is of the form $4k, 4k+1.$
$m^4$is of the form $5k, 5k+1.$
$m^3$ is of the form $7k, 7k+1, 7k+6$ (or for the last one, $7k-1$). 
 
---

## Def - Divisibility
An integer $b$ is said to be divisible by an integer $a \neq 0$ (written $a | b$) if there exists some integer $c$ such that $b=ac$. 

- ex: -12 is divisible by 4 since $-12 = 4(-3)$. Thus $4 \ | -12$.

### Thm 2.2: Props of Divisibility
For integers $a,b,c$, the following hold: 

1. $a \mid 0, 1 \mid a, a\mid a$.
2. $a \mid 1$ $\iff$  $a = \pm 1$.
3. If $a \mid b$ and $c \mid d$, then $ac \mid bd$.
4. If $a \mid b$ and $b \mid c$, then $a \mid c$.
5. $a \mid b$ and $b \mid a$ $\iff$  $a = \pm b$.
6. If $a \mid b$ and $b \neq 0$, then $|a| \leq |b|$.
7. If $a \mid b$ and $a \mid c$, then $a \mid (bx + cy)$ for arbitrary integers $x,y$.

---

## Def - GCD
Let $a, b \in \mathbb{Z}$ with at least one of them different from zero. The greatest common divisor of $a,b$ or gcd($a,b$) is the positive integer $d$ satisfying the following:
- $d | a$ and $d | b$
- If $c | a$ and $c | b$, then $c \leq d$.

Additionally, this can be extended to more than two integers.

### Thm 2.3: Linear Combos + GCD
Given integers $a,b$, not both of which are zero, there exist integers $x,y$ such that $$\gcd(a,b) = ax + by.$$

#### Corollary
If $a,b \in \mathbb{Z}$, not both zero, then the set $$T = \{ax + by | x,y \in \mathbb{Z}\}$$

is precisely the set of all multiples of $d = \gcd(a,b).$

---

## Def - Relatively Prime
 Two integers $a,b$ are relatively prime whenever $\gcd(a,b)=1.$
 
 ### Thm 2.4: Linear Combos + Relatively Prime
  Let $a,b \in \mathbb{Z}$, not both zero. Then $a,b$ are relatively prime $\iff$  there exist integers $x,y$ such that $1 = ax+by$.
  
  For the general case (not 1, but $k$), we know that $gcd(a,b)$  is a factor of $k.$ 
 
 #### Corollary (1)
 If $\gcd(a,b) = d$, then $\gcd(a/d, b/d) = 1$.

#### Corollary (2)
If $a \mid c$ and $b \mid c$ with $\gcd(a,b)$ = 1, then $ab \mid c$.

### Thm 2.5: Euclid's Lemma
If $a \mid bc $, with $\gcd(a,b) = 1$, then $a \mid c$.

### Thm 2.6: GCD + Other Divisors (Equiv Def of GCD)
Let $a,b \in \mathbb{Z}^+$, not both zero. For a positive integer $d$, $d = \gcd(a,b)$ $\iff$ :
1. $d | a$ and $d | b$
2. Whenever $c | a$ and $c | b$, then $c | d$.

#### Lemma

$(a,b) = (a-kb,b) = (a,b-ma)$ for $k, m \in \mathbb{Z}$.

One number can be scaled down while preserving the gcd, so long as the adjustment is in respect to the other number. 

*The proof involves the assumption that $(a,b) = d$ means that $d \mid a, d \mid b$, meaning that $d \mid a-kb, d\mid b$.*

### Thm 2.7: Scalar on GCD
If $k>0$, then $\gcd(ka,kb) = k \gcd(a,b).$

#### Corollary
For any integer $k \neq 0$, we have that $\gcd(ka,kb) = |k|\gcd(a,b).$

### Thm IC: Relating General GCD to Relatively Prime GCD
$(a,b) = d \iff (\frac{a}{d}, \frac{b}{d}) = 1.$

Alternatively, If $(a,b) = d$ and $a = da^', b = db^'$, then $(a^', b^') =1$.

---

## Def: The Euclidean Algorithm
In essence, the Euclidean Algorithm is just repeated uses of the Division Algorithm and the Thm 2.6 Lemma, used before the Fundamental Theorem of Arithmetic. If we want to find the result of $\gcd(a,b)$, then do the following:
$$a = q_1 b + r_1, \qquad 0 < r_1 < b$$
$$b = q_2 r_1 + r_2, \qquad 0 < r_2 < r_1$$
$$a = q_3 r_2 + r_3, \qquad 0 < r_3 < r_2$$

The process continues, until...

$$r_{n-2} = q_n r_{n-1} + r_n, \qquad 0 < r_n < r_{n-1}$$
$$r_{n-1} = q_{n+1} r_n + 0, \qquad 0 < r_1 < b$$

As soon as you hit zero as a remainder, the **previous remainder** is the solution to the GCD problem. 

### Lemma
If $a=qb+r$, then $\gcd(a,b) = \gcd(b,r)$. Applied above, this also means that

$$\gcd(a,b) = \gcd(b,r_1) = \ldots = \gcd(r_{n-1}, r_n) = \gcd(r_n, 0) = r_n.$$

$$(a,b) = (b,r_1) = (r_1,r_2) = \ldots = (r_{n-1}, r_n) = r_n$$

> For example, let's look at $a=1572, b=1112$. Then, $1572 = 1112 (1) + 460$. Next, $1112 = 460(2) + 192$. Following that, $460 = 192(2) + 76$. Then, $192  = 76(2) + 40$, so $76 = 40(1) + 36$, and $40= 36(1) + 4$, and $36 = 4(9)$. So **4** is our GCD. 

### The Extended Euclidean Algorithm
This approach is useful as it also gives the coefficients of the linear combination of numbers that create the original numbers. Go backwards in the Euclidean Algorithm. 

> From our example above: 
> $4 = 40-36$
> $4 = 40 - (76-40) = 2(60) - 76$
> $4 = 2(192-2(76)) - 76 = 2(192) - 5(76)$
> $4 = 2(192)-5(460-2(192)) = 12(192)-5(460)$
> $4 = 12(1112-2(460))-5(460) = 12(1112)- 29(460)$
> $4 = 12()1112) - 29(1572-1112) = -29(1572) + 61(1112)$
> So, $4 = 1572(-29) + 1112(61)$. 



### GCD of More Than Two Numbers with Euclidean

Notice that $(a,b,c) = ((a,b),c) = (a,(b,c)) = (b,(a,c)).$. This extends to more and more numbers inductively. 

For linear combinations, this is similar. $((a,b),c) = (ax+by,c) = (ax+by)t + cs = a(xt) + b(yut) + cs.$ So you may as well write $(a,b,c) = ax+by+cz.$

---
## Def - LCM 
The least common multiple of two nonzero integers $a,b$ denoted $lcm(a,b)$ is the positive integer $m$ that satisfies:
1. $a | m$ and $b| m$.
2. If $a | c$ and $b | c$ with $c > 0$, then $m \leq c$.


### Thm 2.8: GCD + LCM
For positive integers $a,b$: $$\gcd(a,b)lcm(a,b) = ab.$$ This does **not** work for more than two numbers. However, we do have that $$lcm(a,b,c) = lcm(a,lcm(b,c)).$$

#### Corollary
For any choice of positive integers $a,b$, we have that $lcm(a,b) = ab$  $\iff$ $\gcd(a,b)=1.$

Additionally, we can also say that $lcm(a,b) = \dfrac{ab}{\gcd(a,b)}$. 


---
## Sources:
Burton, David M. â€œELEMENTARY NUMBER THEORY,â€ n.d., 452.


## Related:
[[Number Theory Prelims - 202008271247]]

