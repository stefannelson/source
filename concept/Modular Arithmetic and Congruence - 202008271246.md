# Modular Arithmetic 
#math/numbertheory 

# Def: Congruence
Let $n>1$ be an integer. For $a,b \in \mathbb{Z}$, then $a \equiv b \bmod n$ if $n \mid a-b$. 

From the division algorithm, remember that we can write $a = bq + r$. A different way of writing this is $$a \equiv r \bmod{b}.$$

Every integer is congruent to $0,1,2,\ldots,n-1 \bmod{n}$. This/the set $\{0,1,2, \ldots, n-1\}$ is a complete set of **residue classes** mod $n$. It is also the least non-negative complete set of modulo classes mod $n$. 

In general, a set $\{a_1, a_2, \ldots, a_n\}$ of integers is called a **CSRC** if 
$$\{a_1, a_2, \ldots, a_n\} \equiv \{0,1,\ldots, n-1\} \bmod{n}$$
Then,  $\{a_1, a_2, \ldots, a_n\}$ is a CSRC $\bmod{n} \iff a_i \cancel{\equiv} a_j \bmod{n}, i \neq j$.   

> An example of a CSRC is $\{-12,-4,11,13,22,82,91\}$. In terms of $\bmod{7}$, we have that $\equiv \{2,3,4,6,1,5,0\}$. These are all distinct, therefore the original set is CSRC. This carries over in general.
> </n> 
> As a quick note, to get the 2 and 3, we need to **add a factor of 7** since it's negative. 

## Thm: Algebra of Congruences
Pick $n>1 \in \mathbb{Z}$ and $a,b,c,d \in \mathbb{Z}$. Then
1. $a \equiv a \bmod{n}$. This is a reflexive property.
2. $a \equiv b \bmod(n) \implies b \equiv a \bmod n$. (Symmetric)
3. $a \equiv b \bmod n$ and $b \equiv c \bmod n \implies a \equiv c \bmod n$. (Transitive)

These three properties above show that congruence is an **equivalence relation**. 

4. $a \equiv b \bmod n$ and $c \equiv d \bmod n \implies$ $$a+c \equiv b+d \bmod n, \qquad ac \equiv bd \bmod n.$$
5. $a \equiv b \bmod n \implies$ $$a+c \equiv b+c \bmod n,\qquad ac \equiv bc \bmod n \qquad \forall c \in \mathbb{Z}.$$
6. $a \equiv b \bmod n \implies$ $$a^k \equiv b^k \bmod n \qquad \forall k \geq 0.$$ 

> Example 1) Let's show $41 \mid 2^{20}-1$. First, $2^5 =32$, as close to $41$ as we can get. So $32 \equiv -9 \bmod 41$. Square both sides, we get $$2^{10} \equiv 81 \bmod 41 \equiv -1 \bmod 41.$$ Squaring, we can say $$2^{20} \equiv 1 \bmod 41.$$

> Example 2) Let's show $641 \mid 2^{22} + 1$. Starting out: 
> $$641 = 5 \cdot 2^7 + 1$$ This means that $$5 \cdot 2^7 \equiv -1 \bmod 641.$$ So 
> $$5^4 \cdot 2^{28} \equiv 1 \bmod 641$$ which is just 
> $$625 \cdot 2^{28} \equiv 1 \bmod 641$$ 
> $$-16 \cdot 2^{28} \equiv 1 \bmod 641$$ 
> $$-2^4 \cdot 2^{28} \equiv 1 \bmod 641$$ 
> Multiplying by -1, we get $$2^32 \equiv -1 \bmod 641. \checkmark$$

## Thm: Cancellations with Congruences 

We know that if $ac=bc, c\neq 0,$ then $a=b.$. Is this true for congruences? It's complicated...

Let $c\cancel{\equiv} 0 \bmod n$. Then $$ac \equiv bc \bmod n \implies a \equiv b \bmod \frac{n}{\gcd(n,c)}.$$

### Corollary 1
Given $ac \equiv bc \bmod n$, if $\gcd(n,c)=1$, then $a \equiv b \bmod n$. 

### Corollary 2
If $\gcd(a,n)=1$, then $\{ 0,a\cdot 1, a \cdot 2,\ldots, a(n-1)\}$ is a (CSRC) $\bmod n$.

### Corollary 3 *
Suppose $p$ is prime and $p \cancel{\mid} a$. Then $\{0,a,2a,\ldots,(p-1)a \}$  is a CSRC $\bmod p$.

### Corollary 4: Fermat's Little Theorem
Let $p$ be prime and $a \in \mathbb{Z}$ such that $p$ does not divide $a$. By Corollary 3, $$\{a,2a,\ldots,(p-1)a\} \equiv \{1,2,\ldots,p-1\} \bmod p.$$

Following this, notice that we have 

$$a \cdot 2a \cdot \ldots \cdot (p-1)a \equiv 1 \cdot 2 \cdot \ldots \cdot (p-1) \bmod p.$$

$$$a^{p-1}(p-1)! \equiv (p-1)! \bmod p.$$

We know that $p \cancel{\mid} (p-1)!$, so they're relatively prime. This implies that $$\boxed{a^{p-1} \equiv 1 \bmod p}.$$

> Alternatively, Let $m$ be prime and $a \in \{1, 2, \ldots, m-1 \}$. Then, $$a^{m-1} \equiv 1 \mod m.$$

# Def: Linear Congruence
A linear congruence is an equation of the form 

$$ax \equiv b \bmod n,$$
 
where $n>1$ is an integer and $a,b \in \mathbb{Z}$ and $a \cancel{\equiv} 0 \bmod n$. 

This would produce *finitely many* solutions $x_0 \bmod n$. Three main questions should be asked:
1. When does such an equation (Linear Congruence) have solutions? 
2. If a solution exists, 
	* how do we find it? 
	* how many are there? 

> Example: Let's look at 
> $$ \begin{align*}
> 2x &\equiv 1 \bmod 6 \\
> 3x &\equiv 3 \bmod 6 \\
> 5x &\equiv 1 \bmod 6. \\
> \end{align*}$$
> The first eqn says that $2x=1+6k \rightarrow \cancel{2(x-3k)  =1}.$ So no solution exists in this one.
> Next, the second eqn shows $3(1) \equiv 3, 3 \cdot 3 \equiv 3, 3 \cdot 5 \equiv 3 \bmod 6$. So there's three solutions; $x \equiv 1,3,5$.
> Finally, the last eqn has only one unique solution; $x \equiv 5$.

## Thm: When Does a LC have Solutions? How to Find?
$ax \equiv b \bmod n$ has solutions $\iff$ 

$$\begin{align*}
\gcd(a,n) \mid b.
\end{align*}$$

> Example: Consider $12x \equiv 9 \bmod 45$. Find one solution using the above theorem plus the Euclidean Algorithm. 
> First, $\gcd(12,45) = 3 \mid 9$. Expressing the gcd as a linear combination:
> $$\begin{align*}
12(4) + 45(-1) &= 3 \\
{} \\
\text{Multiply both sides by three..} \\
{} \\
12(12) + 45(-3) &= 9 \\
{}\\
\text{Mod 45 both sides..} \\
{}\\
12 \cdot 12 &\equiv 9 \bmod 45.
> \end{align*}$$

## Thm: How many sols to LCs exist?
Assume $\gcd(a,n) = d, d \mid b$. Let $x_0$ be a solution Then **all solutions** of $ax \equiv b \bmod n$ are given by.

$$\{x_0, x_0+d, x_0+\frac{n}{d}, x_0 + 2\frac{n}{d}, \ldots, x_0 + (d-1) \frac{n}{d}\}.$$

We therefore have exactly $d$ **distinct** solutions. 

> Example: From above, then congruence $12x \equiv 9 \bmod 45$ has three solutions, as $\gcd(12,45) = 3$. We found $x_0 = 12$ before, so then $12+1\cdot 15, 12 + 2\cdot 15$ are also solutions. So, all solutions are given by 12,27,42. $\checkmark$

### Corollary: LC, Relatively Prime
If $\gcd(a,n) = 1$, then the linear congruence $ax \equiv b \bmod n$ **always has one unique solution**. 

In particular, $ax \equiv 1 \bmod n$ has a unique solution - that is, its **multiplicative inverse** of $a \bmod n$. 

The multiplicative inverse of $a \bmod n$ exists $\iff \gcd(a,n)=1.$ If $\gcd(a,n) =1$ and we know the multiplicative inverse $a^{-1}$, the unique solution of $$ax \equiv b \bmod n$$ is given by $$x \equiv a^{-1}b \bmod n.$$

> Example: Solve $4x \equiv 3 \bmod 15$. The numbers 4,15 are relatively prime. 
> The multiplicative inverse $\rightarrow 4^{-1} \equiv 4 \bmod 15$. So $x \equiv 12 \bmod 15.$


*In RSA, if we have $n=pq$ where $p,q$ are large primes. Choose $e$ such that $\gcd(e, \phi(n)) =1$. The public key is thus $n,e$. Anyone can encrypt: 
$$m^e \bmod n.$$
The secret key is $p,q,d$ where $d = e^{-1} \bmod \phi(n)$. Finding the multiplicative inverse is not easy.*

> Example: Let's find the mult inverse of $17 \bmod 276$. 
> Effectively, this means that we are looking to solve $17x \equiv 1 \bmod 276$. Remember finding **a** solution means finding **the** solution here. Apply the Euclidean Algorithm. 
> 
> $$\begin{align*}
276 &= 17(16) + 4 \\
17 &= 4(4) + \boxed{1} \\
4 &= 4(1) + 0
\end{align*}$$
> Then, extended Euclidean Algorithm. 
> $$\begin{align*}
1 &= 17 - 4(4) \\
  &= 17-4(276-16(17)) \\
  &= 65(17) -4(276).
\end{align*}$$
> Reduce mod 276, obtaining
> $$\begin{align*}
65(17) \equiv 1 \bmod 276
\end{align*}$$
> Thus, the mult inverse is 65.  Or, $17^{-1} \equiv 65 \bmod 276. \quad \checkmark$

---
# Thm: Chinese Remainder Theorem
Suppose we are trying to solve 

$$\begin{align*}
a_1x &\equiv b_1 \bmod{m_1} \\
a_2x &\equiv b_2 \bmod{m_2} \\
&\ldots \\
a_kx &\equiv b_k \bmod{m_k}
\end{align*}$$

with $\gcd(m_i, m_j) = 1, i \neq j$. Then without loss of generality (assuming we have done all the possible cancellations), we can assume $\gcd(a_k, m_k) = 1$ for all $k$. So, their multiplicative inverses $a^{-1}_i$ exist mod $m_i$. The system then changes into

$$\begin{align*}
x &\equiv c_1 \bmod{m_1} \\
x &\equiv c_2 \bmod{m_2} \\
&\ldots \\
x &\equiv c_k \bmod{m_k} \\
\end{align*}$$

So here's the theorem. If $\gcd(m_i, m_j)=1, i\neq j$, then the first system listed above **has a unique solution $\bmod m_1m_2\ldots m_k$**. Specifically, the product of each of the system's moduli.  

> Example: Find the solution to the system 
> $$\begin{align*}
x &\equiv 1 \bmod{2} \\ 
x &\equiv 2 \bmod{3} \\ 
x &\equiv 3 \bmod{5} \\ 
\end{align*}$$
> Two approaches can be done here. First, $N_1 = 3(5), N_2 = 2(5), N_3 = 2(3)$. So $x_1 = 15^{-1} \bmod{2}$, so $x_1 = 1$. Next, $10x_2 \equiv 1 \bmod{3}$, so $x_2 = 1$. Finally, $6x_3 \equiv 1 \bmod{5}$, so $x_3=1$. 
> From here, $x = 15(1)(1) + 10(1)(2) + 6(1)(3) = 15+20+18 \equiv 23 \bmod{30}.$ This is the smallest value that works in each equation in the above system!
> </n>
> The second method: start with the biggest modulo, $x \equiv 3 \bmod{5}$. Then we can write $x = 3+5k, k \in \mathbb{Z}$. Put this into the second congruence: $3+5k \equiv 2 \bmod{3}$. From here, $2k \equiv 2 \bmod{3}$ ending up with $k \equiv 1 \bmod{3}$. But this means that $k = 1+3n, n \in \mathbb{Z}$. Thus $x = 3+5k=3+5(1+3n) = 8+15n$. Put this back into the first congruence: $$8+15n \equiv 1 \bmod{2}.$$
> From here, you get the $n \equiv 1 \bmod{2}$ or $n=1+2m, x=8+15(1+2m) = 23+30m$. 

Now, let's go back to the previous example: 

> Example: Find $17^{-1} \bmod{276}$. This creates 
> $$\begin{align*}
17x &\equiv 1 \bmod{3} \\
17x &\equiv 1 \bmod{4} \\
17x &\equiv 1 \bmod{23} \\
\end{align*}$$
> We need to convert these: 
> $$\begin{align*}
2x &\equiv 1 \bmod{3} \rightarrow x \equiv 2 \bmod{3}\\
x &\equiv 1 \bmod{-4} \rightarrow x \equiv 1 \bmod{4}\\
-6x &\equiv 1 \bmod{23} \rightarrow x \equiv -4 \equiv 19 \bmod{23}\\
\end{align*}$$
> So, after the right arrows is our new setup. If we use the first approach, it could get messy: $N_1 = 92, N_2 = 69, N_3 = 12$. So $92x_1 \equiv 1 \bmod{3}  \rightarrow 2x_1 \equiv 1 \bmod{3} \rightarrow x_1=2$. Similarly, $N_2 \rightarrow x_2=1, N_3 \rightarrow x_3 =2$. So 
> $$x = N_1x_1a_1 + N_2x_2a_2 + N_3x_3a_3 = 92(2)(2) + 69(1)(1) + 12(2)(19) \equiv  65 \bmod{276}$$

---

# Thm: Wilson's Theorem
If $p$ is prime, then $$(p-1)! \equiv -1 \bmod{p}.$$

> Example: Taking $37! \equiv ? \bmod{41}$. By Wilson, we have that 
> $40! = 1 \bmod{41}$ but that means we have $40 * 39 * 38* 37! \equiv 1 \bmod{41}$. Replacing these removed values with equivalent ones, 
> $$-1 * -2 * -3 * 37! = 6*37! \equiv 1 \bmod{41}.$$
> We can multiply both sides by 7 (the inverse) to get
> $$37! \equiv 7 \bmod{41}.$$

Other applications include the solvability of sum of two squares, gaussian integers, etc. 

## Corollary: App for Odd Primes
If $p$ is an odd prime ($4k\pm 1$), then $x^2 \equiv -1 \bmod{p}$ has solutions $$\iff p = 4k+1$$ 

# Thm: Choose + Odd Primes
If $p$ is an odd prime, then $$p \mid \binom{p}{k}$$ for all $1 \leq k \leq p-1$.

## Corollary: Freshman's Dream

^1be369

If $p$ is prime, then $$(a+b)^p \equiv a^p + b^p \bmod{p}$$ for all $a,b \in \mathbb{Z}$.

# Def: Reduced/Least Set of Residue Classes
Let $n>1$ be an integer. A set $\{a_1,a_2, \ldots, a_k\}$ is a RSRC mod n if:
* $\gcd(a_i,n) = 1$ for each $i$.
* $a_i \neq a_j \bmod{n}, i \neq j$.  

> Let $p$ be prime. Remember a complete set of residue classes shown above
$$\{ 0,1,\ldots,p-1 \} \text{ or } \{ 1,2,\ldots, p-1 \}$$
The ones on the right side are all relatively prime to $p$ - a reduced set of residue classes (RSRC). 
Now, what we have a composite number instead? For example, $\{0,1,2,3,4,5,6,7\}$ is a CSRC $\bmod 8$. The reduced set of residue classes in this case is $\{1,3,5,7\}$. 

If $1 \leq a_i < n$, then $\{a_1, a_2, \ldots, a_k\}$ is the **least set of residue classes**. 




# Related:
[[Number Theory Prelims - 202008271247]]
[[Divisibility Theorems in the Integers - 202008271248]]
[[Prime Numbers & Factorization - 202008271332]]
[[Euler's Phi Function - 202012040015]]