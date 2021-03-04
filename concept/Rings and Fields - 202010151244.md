# Rings and Fields
#math 


# Def: Ring
Let $R$ be an non-empty set and $+,\cdot$ on $R$. Then $R$ is called a ring if the following properties hold. ^54ea13
1. $(R,+)$ is an [[Groups - 202009291317#^76080d | Abelian Group]]. 
2. The operation $\cdot$ is asscociative. 
3. The distributive property holds with both operations. That is, for any $a,b,c \in R$, $$a\cdot (b+c) = a\cdot b+a\cdot c \qquad\text{and}\qquad (b+c)\cdot a = b\cdot a + \cdot a.$$

## Some observations 

Notice that since $(R,+)$ is a group, an identity exists with respect to the operation $+$, denoted $0_R$, where $$a+0_R = 0_R +a = a \quad\forall a \in R$$

Additionally, if $a\cdot 1_R=1_R \cdot a = a$, the element $1_R$ is just called an **identity**. A ring may or may have an (multiplicative) identity.

Finally, if $ab=ba$ for all $a,b \in R$, then $R$ is said to be a **commutative ring**. Remember, addition commutativity doesn't matter because of property 1. A ring may or may not be commutative. 

> Some examples: $\mathbb{Q}, \mathbb{R}, \mathbb{C}, \mathbb{Z}$ are all commutative rings with identity. More importantly for finite fields, $(\mathbb{Z}_n, \oplus, \odot)$ is also a commutative ring with identity. Next, some that are commutative without identity is $(2\mathbb{Z},+,\cdot)$, which is infinite, and $(2\mathbb{Z}_{4},\oplus,\odot)$, which is finite. Notice that $(2\mathbb{Z}_{10},\oplus,\odot)$ DOESN'T work, because $1_{2\mathbb{Z}_{10}} = 6$. Next, a ring that isn't commutative $\mathbb{Z}^{n \times n}$ under matrix addition, multiplication, but has identity. Finally, a noncommutative ring without identity is the set of matrices with even entries, which is infinite, and $2 \times 2$ matrices with entries in $2\mathbb{Z}_8$, which is finite (exercise, find two matrices that do not commute in this ring). 


# Def: Zero Divisors
Let $R$ be a commutative ring with identity. A element $b \neq 0 \in R$ is a zero divisor if $$b\cdot c = 0$$ for some $c \neq 0$. 

Other than this, we can prove that $a \cdot 0 = 0$ for all $a \in R$ using the distributive property. For the above definition, we must insist that neither element is 0, but their product is. 

Asking whether an element is a zero divisor is equivalent to asking whether it has a additive inverse.


# Def: Units
Let $R$ be a commutative ring with identity. An element $u \in R$ is called a unit if there exists $v \in R$ such that $$u \cdot v = 1.$$ In commutative rings, the identity is a unit!

> Some examples: There are no zero divisors in $\mathbb{Z}$, but the units are $\{-1,1\}$. In $\mathbb{Q}$, there are no zero divisors but the units are every element in $\mathbb{Q}/\{0\}$. Something like $\mathbb{Z}_6$ has zero divisors $\{2,3,4\}$ and units $\{1,5\}$. In general ($\mathbb{Z}_n$), the units are elements relatively prime to $n$.

Asking whether an element is a unit is equivalent to asking whether it has a multiplicative inverse.

## Prop: Zero Divisor and Units
If $R$ is a commutative ring with identity $(R \neq 0)$, then an element cannot be a zero divisor and unit at the same time. 

> To prove, assume an element $u$ is both a unit and zero divisor. A contradiction arises where a separate element has to be zero. 

### Corollary
If $p$ is prime, no are no zero divisors in $\mathbb{Z}_p$.

## Prop: Partitioning Finite Rings
If $R$ is a finite commutative ring with identity, then any non-zero element in $R$ is either a unit or a zero divisor. 

> To prove, assume that some element is not zero and not a zero divisor. Then, it has to be a unit. The trick is to scale your ring by this element - that is $aR = \{ar \mid r \in R\} \subseteq R$. Those products are all different since otherwise it'd be a zero divisor since if you assume the contradiction, there'd be $ar_1 = ar_2$. So, these sets are the same size. From here, we'd need the set to be finite/denumerable to say that they are thus the same set $\rightarrow aR = R$. So, $aR$ must have the identity, meaning there is some $r$ such that $ar = 1$, meaning $a$ is a unit! 

# Def: Field/Integral Domain
Let $R$ be a commutative ring with identity. If $R$ has no zero divisors, then $R$ is called an **integral domain** (ID). 

That is, $R$ is an integral domain $\iff$ for $a,b \in R, ab=0$ implies $a=0$ or $b=0$.

Also, if every non-zero element in $R$ is a unit, then $R$ is called a **field**. The relation between these two definitions is that **all fields must be integral domains**. However, not every integral domain is a field (see $\mathbb{Z}$ - integral domain but not a field).

## Thm: Field <-> Integral Domain (Finite)
A *finite* ring $R$ is a field $\iff$ it's an integral domain. In particular, $\mathbb{Z}_n$ is a field iff $n$ is prime iff it's an ID. 

In this case $\mathbb{Z}_p$ is known as a **prime field**. 


## Thm: Cancellation Property in IDs
If $R$ is an ID and $a \neq 0 \in R$, then $$ab=ac \implies b=c.$$

Indeed, $ab = ac \implies a(b-c)=0$. But since $R$ is an ID, then we must have either $a=0, b=0$. Since $a \neq 0$, then we have that $b=c$.

> The ID portion is essential. For example, in $\mathbb{Z}_8,\quad 2(2) = 2(6)$, but $2 \neq 6$.

# Def: Subrings
Let $R$ be a commutative ring, $S \subseteq R$ is a nonempty subset. Then, $S$ is called a **subring** of $R$ if $S$ is a ring under the same operations. That is for 
$$(R,+,\cdot) \implies (S, +, \cdot) \text{   is a ring.}$$

## Thm: Subring Criteria
Define ring $(R,+,\cdot)$. Then $S \subseteq R$  is a subring $\iff$
1. $a-b \in S$
2. $a \cdot b \in S$ 

$\forall a,b \in S$. 

# Def: Ideal
Define $(R,+,\cdot)$ as a commutative ring. A nonempty subset $I \subseteq R$ is an **ideal** of $R$ if: 
1. $a-b \in I \quad\forall a,b \in I$.
2. $a \cdot r \in I \quad\forall a \in I$ **AND $r \in R$**.

> Works like a black hole - *swallows* multiplication.

## Rmk: Subring/Ideal Connections
Note that **any ideal is a subring**. But, is the converse - are all subrings ideals - true? Nah dude. 

An example of this is $\mathbb{Z} \subseteq \mathbb{Q}$. If $m,n \in \mathbb{Z}$ then $m-n, m\cdot n \in \mathbb{Z}$ as well. So $\mathbb{Z}$ is a subring of $\mathbb{Q}$. But notice that $\frac{1}{2} \in \mathbb{Q}$, but $1 \cdot \frac{1}{2} = \frac{1}{2}$ which is not in $\mathbb{Z}$. So, a subring that isn't an ideal. 

> Other ideals of a general ring $R$ include $R$ itself and $\{0\}$. In $\mathbb{Z}$, then $3\mathbb{Z} = \{\ldots,-3,0,3,\ldots\}$ is an ideal of $\mathbb{Z}$. In fact, $m\mathbb{Z}$ works for any integer $m$. 

Other than the examples above, let's think modular - for $\mathbb{Z}_7$ (main key here is that 7 is prime), the only ideals are $0, \mathbb{Z}_7$. In fact, for primes, there are no trivial ideals. $\mathbb{Z}_8$ has quite a few!

## Thm: Fields and Ideals Connections
If $F$ is a field, then $\{0\}$ and $F$ are the only ideals $F$. 

Moreover, if $R$ is a commutative ring with identity $1$ and $\{0\}, R$ are the only ideals, then **$R$ has to be a field**. 

> #idea This definition looks A LOT like the definitions for prime numbers...

> Let $a\neq 0$ in $R$. Then the set $aR$ is an ideal. If $a \neq 0$, then $aR \neq \{0\}$. By our hypothesis, $aR=R$, so $1 \in R = aR \implies ar = 1$ for some $r\in R$. This means that $a$ is a unit, thus $R$ is a field.  

### Lemma: (for above)
Let $I$ be an ideal of $R$. If $I$ *contains a unit*, then $I = R$.

> Proof: Let $u$ be a unit, $u \in I \implies \exists v \in R$ such that $u\cdot v =1$. But since $I$ is an ideal, $u \cdot v \in I \implies 1 \in I$. Then $1r = r\in R$ for every $r \in R$. This means that $R \subseteq I$, thus they are the same. 

# Def: Principal Ideals
Define commutative ring with identity $(R,+,*)$. Let $a\in R$ be an element. Then, $\langle a \rangle = aR = \{ar \mid r \in R\}$ is an ideal of $R$. This is called a **principal ideal generated by $a$**. 

Notice that both $R, \{0\}$ are principal ideals since $R = \langle 1 \rangle, \{0\} = \langle 0 \rangle$.

> In $\mathbb{Z}$, all ideals are principal. That is $$\langle m \rangle = m\mathbb{Z} = \{\ldots,-m,0,m,\ldots\} = \langle -m \rangle$$
> So we just need to consider generators that are positive integers. 

## Lemma: Relationships between principal ideals
Let $R$ be a commutative ring with $1$ (the identity). Then for $a,b \in R$, then
$$\langle a \rangle \subseteq \langle b \rangle \iff a = b\cdot r$$
for some $r\in R$. In particular,
$$\langle a \rangle = \langle b \rangle \iff a = b\cdot u$$
for some **unit** $u \in R$.

## Def: Ideals of Z_n
In $\mathbb{Z}$, if $a,b \in \mathbb{Z}+$, we know from previous results that 
$$\langle a \rangle \subseteq \langle b \rangle \iff b \mid a.$$

In $\mathbb{Z}_n$, all ideals are principal and they are generated by $\langle a \rangle$ where $a\in \mathbb{Z}+$ and $a \mid n$. 

> In $\mathbb{Z}_{12}$, the positive divisors of 12 are $1,2,3,4,6,12$, so the ideals are $$\langle 1 \rangle ,\langle 2 \rangle, \langle 3 \rangle,\langle 4 \rangle, \langle 6\rangle, \langle 12 \rangle.$$
> This works in general, and describes all **distinct** ideals of your domain.  Intriguingly, the smallest generator creates the largest ideal, and vice versa. 

This leads to the **ideal lattice**.  ^eeab2c

>For $\mathbb{Z}_{12}$, the ideal lattice looks like the following, which each connection showing that the previous is a subset:
></n> 
>![[Pasted image 20201020135740.png]]

---

# Def: Polynomial Rings
Let $R$ be a commutative ring with identity. We define
$$R[x] := \{a_0 + a_1x _+ \ldots + a_nx^n \mid n \geq 0, a_i \in R\}.$$

For it to be a ring, we need the operations: Define $p(x) = a_0 + a_1x _+ \ldots + a_nx^n, q(x) = b_0 + b_1x _+ \ldots + b_mx^m$. Then, we have
$$p(x)+q(x) = (a_0+b_0) + (a_1+b_1)x + \ldots$$
and
$$p(x)q(x) = a_0b_0 + (a_1b_0 + a_0b_1)x + \ldots + \left(\sum_{0 \leq 1 \leq k}a_ib_{k-i}\right)x^k + \ldots$$

So, $(R[x],+,\cdot)$ is a commutative ring with identity, $1_{R[x]}=1_R=1$.

## Def: Degree of a Polynomial
Define $$p(x) = a_0 + a_1x _+ \ldots + a_nx^n.$$ Then $n$ is the **degree** of $p(x)$, denoted deg$(p)$. Also, $a_0$ is the **constant term** while $a_n$ is the **leading coefficient**. 

## Prop: Degree of Poly Sum
We have that deg$(p(x)+q(x)) \leq \max\{\deg(p), \deg(q)\}$. 

So, if $\deg(p) \neq deg(q)$, then $\deg(p+q)=\max\{\deg(p), \deg(q)\}$

It can also be a strict inequality - take $p(x)=-2x^3+x+1, q(x) = 2x^3-1$, then the sum decreases the degree significantly; that is $\deg(p+q)=1$.

## Thm: Degree of Poly Product
If $R$ is an integral domain and $p(x),q(x) \in R[x]$, then the $\deg(p(x)q(x)) = \deg(p)+\deg(q)$. 

So, **some remarks**: 
1. If $p(x)=a_0, a_0 \neq 0$, then $\deg(p(x))=0$. 
2. But a special case - $\deg(0) = -\infty$. The zero polynomial is also the additive identity of the polynomial ring. 
3. If $R$ is **not an integral domain**, this theorem **does not hold**. For example, if $R = \mathbb{Z}_4, p(x)=1+2x, q(x)=1-2x$, then the product $p(x)q(x) = 1-4x^2=1$. So the degree is 0 while the degrees of the original polynomials are both 1. Welp. 
4. For arbitrary ring $R$, we have that $R \subseteq R[x]$ subring. 

## Thm: ID Carries over to Poly Ring
The polynomial ring $R[x]$ if an integral domain $\iff$ $R$ is an integral domain. 


## Thm: Division Algorithm - Poly Rings Over **Fields**
Let $F$ be a field, then $F[x] = \{a_0+a_1x_\ldots+a_nx^n \mid a_i \in F\}$. Then, there is a division algorithm! 

Take $a(x),b(x) \in F[x], b(x) \neq 0$. Then there exists $q(x),r(x) \in F[x]$ such that $$a(x) = b(x)q(x) + r(x),\qquad r(x) = 0 \text{  or  } \deg(r(x)) < \deg(b(x)).$$

> Of course, if the coefficient ring is **not a field, division might not work**. For example, on $\mathbb{Z}[x]$, cannot divide $x^2$ by $2x$.

### Rmk: Some Consequences of Div Algorithm
1. **Divisibility**: Define $p(x), q(x) \in F[x], p(x)\neq 0$. We say that $p(x) \mid q(x)$ if there exists some $a(x) \in F[x]$ such that $q(x) = p(x)a(x)$.
2. Properties of divisibility work very similarly:
	1.  $p(x) \mid q(x) \implies \deg(p) \leq \deg(q)$ or $q \geq 0$. 
	2.  $p(x) \mid q(x), q(x) \mid r(x) \implies p(x) \mid r(x)$.

3. A difference though, if $p(x)\mid q(x)$ and $q(x)\mid p(x)$, then $p(x)=cq(x)$ where $c \in F/\{0\}$. It's a **constant multiple**.
4. **Greatest Common Divisor (gcd)** works the same as in integers. We have $d(x) = \gcd(p(x),q(x))$ if:
	1. $d(x) \mid p(x)$ and $d(x) \mid q(x)$.
	2. If $c(x) \mid p(x)$ and $c(x)  \mid q(x)$, then $c(x) \mid d(x)$.
5. **Extended Euclidean/Bezout's Lemma**: If $d(x)=\gcd(p(x),q(x))$, then there exists $a(x),b(x) \in F[x]$ such that $$d(x) = a(x)p(x) + b(x)q(x).$$ It's unique **up to a unit multiple**. 
6. The $\gcd(p(x),q(x))=1 \iff p(x)a(x) + q(x)b(x)=1$ for some $a(x),b(x) \in F[x]$. 

### Rmk: (Lack of) Uniqueness of GCD
The GCD is unique up to a nonzero constant multiple. That is, if $d(x) = \gcd(p(x),q(x))$, then $cd(x)$ is also the gcd for all $c \in F/\{0\}$.

However, the GCD is unique if we insist on the GCD to be "*monic*". That is, the leading coefficient is 1.  Remember, that you can make any polynomial monic, even in something like $\mathbb{Z}_7[x]$ (think about the inverses).

> Ex: Consider $p(x)=x^2+x+1, q(x)=x+1$ over $\mathbb{Z}_2[x]$. Let's express the GCD as a linear combination of these two polynomials using the Extended Euclidean Algorithm:
> $$\begin{align*}
x^2+x+1 &= (x+1)x + \boxed{1} \\
&\vdots\\
1 &= (x^2+x+1)-(x+1)x
\end{align*}$$
>  Another example, consider $p(x)=x^5+1, q(x)=x^2+1$ in $\mathbb{Z}_2[x]$. Then,
>  $$\begin{align*}
x^5+1 &= (x^2+1)(x^3+x) + \boxed{(x+1)} \\
x^2+1 &= (x+1)(x+1) + (0) \\
&\vdots \\
\gcd = x+1 &= (x^5+1)\cdot 1 - (x^2+1)(x^3+x)
\end{align*}$$

---
Post-E2 Material
---

# Def: Irreducible Polynomials
Polynomial $p(x) \in F[x]$ is called irreducible if $a(x) \mid p(x)$ implies that $a(x) \in F[x]/\{0\}$ or $a(x) = p(x)\cdot c,\quad c\in F/\{0\}$. 

In other words, $p(x)$ is reducible if $p(x)=a(x)b(x)$ where $1 \leq \deg(a), \deg(b) < \deg(p)$. These are analogous structures to prime numbers.

> For example, $x^2+1 \in \mathbb{R}[x]$ is irreducible. However, it's reducible in $\mathbb{F}_2[x]$ since $x^2+1 = (x+1)^2$ in this ring. 
> Next, $x^2+x+1$ is irreducible over $\mathbb{Z}_2$, but not $\mathbb{Z}_3$ since $x^2+x+1 = x^2-2x+1 = (x-1)^2$ in this ring. 

# Thm: Fundamental Theorem of Arithmetic (for Polynomials)
If $p(x) \in F[x], \quad \deg(p) > 0$, then there exists irreducible polynomials $a_1(x), a_2(x), \ldots, a_k(x) \in F[x]$ such that $p(x) = a_1(x)\ldots a_k(x)$. 

This unique polynomial factorization is unique. That is, if $p(x) = a_1(x)\ldots a_k(x) = b_1(x)\ldots b_m(x)$, then we must have $k=m$ and (after a reordering if needed) $b_i(x)=c_i \cdot a_i(x), \quad c_i \in F/\{0\}$. 

# Thm: Every Poly Ideal is Principle
Every ideal in $F[x]$ is principle. That is, if $I$ is an ideal of $F[x]$, then $I$ is generated by a single polynomial:
$$I = \langle p(x) \rangle$$
for some $p(x) \in F[x]$. Additionally, $I$ is generated by a polynomial of minimal degree, which is unique if we insist this polynomial to be monic. Otherwise, there are many of these generators.

Constructing Finite Fields - Prereqs
---

# Def: Quotient Rings
Let $I$ be an ideal in $R$. By $a+I$, we denote a **coset** of $I$. Here, 
$$a+I = \{a+r \mid r \in I\}.$$

Cosets are equivalence classes, so they partition the ring. That is, the union of all cosets form the ring, and all cosets are either disjoint or identical. We can think about these "slices" as elements of a ring structure. We'll need operations that are well-defined in this ideal structure. We define

$$R/I := \{a+I \mid a \in R\}.$$

> For example, consider when $R = \mathbb{Z}, I = 3\mathbb{Z}=\langle 3 \rangle$. Then, $$R/I = \{3\mathbb{Z}, 1+3\mathbb{Z}, 2+3\mathbb{Z}\}.$$
> This represents all elements that are $0 \pmod{3}$ and so on - the residue classes of $\mathbb{Z}_3$.
> </n>
> In polynomial rings, consider $\mathbb{Q}[x], \quad I=\langle x^2 \rangle$. Then, consider the coset
> $$a_0+a_1x+\ldots+a_nx^n + \langle x^2 \rangle$$
> Every term $x^2$ or higher gets absorbed since they're all "multiples" of $x^2$, so we really have $a_0+a_1x+\langle x^2 \rangle$. So,
> $$R/I = \{a+bx+I \mid a,b \in \mathbb{Q}\}.$$

For a similar example, 

> Let $R=\mathbb{Z}_2[x], \quad I = \langle x^2 \rangle$, then $R/I = \{a+bx+I \mid a,b \in \mathbb{Z}_2\}$. But this is a set of four elements: $\{\bar{0} ,\bar{1} ,\bar{x} ,\bar{1+x}\}$.
> </n>
> Now, how do we turn this into a ring? We define the two operations:
> 1. $(a+I)+(b+I) = (a+b)+I$.
> 2. $(a+I)(b+I) = ab + I$.
> </n> 
> These operations are well-defined, i.e. if $a_1+I=a_2+I$ and $b_1+I=b_2+I$, then $(a_1+b_1)+I = (a_2+b_2)+I$ and $(a_1b_1)+I=(a_2b_2)+I$. The ideal structure is needed for multiplication to work. 


So, $(R/I, +, \cdot)$ becomes a ring. If $R$ is commutative with identity, then so is our new ring!

> Another example, with $\mathbb{Z}/3\mathbb{Z} = \{\bar{0}, \bar{1}, \bar{2}\}$, then $\bar{2}\cdot\bar{2}=\bar{1}$ which is perfect. 
> </n>
> Next, consider $F[x]/\langle x \rangle = \{a+ \langle x \rangle \mid a \in F\}$ Remember, $$\langle x \rangle = \{x \cdot p(x) \mid p(x) \in F[x]\}.$$ This is equivalent to $\{\bar{a} \mid a \in F\} = F$. So it acts exactly like this arbitrary field. 
> </n>
> Finally, $\mathbb{Z}[x]/\langle 2,x \rangle = \{a+\langle 2,x \rangle \mid a \in \mathbb{Z}\}$. But anything that are multiples of 2 are absorbed into this ideal. So, instead we can write
> $$=\{a+ \langle 2,x \rangle \mid a = 0 \text{ or } 1\} = \mathbb{Z}_2.$$

# Def: Maximal Ideals
Let $R$ be a ring, then an ideal $M$ of $R$ is said to be **maximal** if $M \neq R$ and there is no proper ideal $J$ such that $M \subset J \subset R$. That is, if $J$ is an ideal of $R$ such that $M \subseteq J$, then either $J=M$ or $J=R$.

Looking back at the [[Rings and Fields - 202010151244#^eeab2c | ideal lattice]], maximal ideals are the ones that are connected to $R = \langle 1 \rangle$ with one arrow/segment. Basically, one level below. 

> Examples: In $\mathbb{Z}$, we have that $\langle a \rangle$ is maximal $\iff$ $a$ is prime. This is because $\langle a \rangle \subseteq \langle b \rangle \quad\iff\quad b \mid a$
> </n>
> In $\mathbb{Z}_n, \quad \langle a \rangle$ is maximal $\iff$ $a$ is a prime divisor of $n$. In $\mathbb{Z}_{12}$, the maximal ideals are $\langle 2 \rangle, \langle 3 \rangle$. 

If $F$ is a field, the maximal ideal is $\{0\}$, and **is the only one**. This is the defining characteristic of fields. 

## Thm: Comm Rings w/ 1 -> Fields
If $R$ is a commutative ring with identity, $R$ is a field $\iff$ $\{0\}$ is the maximal ideal. 

## Thm: Properties of Maximal Ideals
1. Every element is maximal ideal $M$ is **not** a unit/is a non-unit. This is from a previous remark - if there is a unit, the ideal automatically becomes the ring itself.
2. A proper ideal $M$ of $R$ is maximal $\iff$ $$\langle M,x \rangle = R \quad \forall x \in R/M.$$
3. **IMPORTANT** Define $R$ to a be a commutative ring with identity Let $M$ be a proper ideal of $R$. Then, $M$ is maximal $\iff$ $R/M$ is a field.

## Thm: Maximal Ideals + Irreducible Polys
Let $F$ be a field. An ideal $\langle p(x) \rangle$ in $F[x]$ (automatically principle) is maximal $\iff$ $p(x)$ is an irreducible polynomial. 

Combining this with property (3) from above, and we can construct a new field!

> Recall that $x^2+x+1$ is irreducible in $\mathbb{Z}_2[x]$. That is, $\langle x^2+x+1 \rangle$ is maximal in $\mathbb{Z}_2[x]$. So, we know that $$\mathbb{Z}_2[x]/\langle x^2+x+1 \rangle \text{   is a field.}$$
> This is equal to the set $\{a_0+\ldots+a_nx^n + \langle x^2+x+1 \rangle\}$. We can express every power of $x$  into a couple initial terms. So, we can express it as follows: $$\{a_0+a_1x+\langle x^2+x+1 \rangle \mid a_0,a_1 \in \mathbb{Z}_2\} = \{\bar{0},\bar{1},\bar{x},\bar{1+x}\}.$$
> Taking $\bar{x} \rightarrow \omega$ where $\omega^2 = 1+\omega$ and $\omega(1+\omega)=\omega+\omega^2=1$. From here, we can construct the following tables: 
> ![[Pasted image 20201027140024.png]]
> This ($\{0,1,\omega,1+\omega\}$) **is a field of size four** since every element has a unit and inverse!

---

# Def: Characteristic of a Field (or any Ring)
Let $F$ be a field. The **characteristic** char$(F)$ is the additive order of $1$, the multiplicative identity. That is - it's the smallest positive number $r$ such that $r \cdot 1 = \underbrace{1+1+1+1+\ldots+1}_r = 0$. If such a positive integer $r$ does not exist, then we just say that char$(F)=0$.

> Examples: Consider that char$(\mathbb{R})=\text{char}(\mathbb{Q})=0$. For finite fields, char$(\mathbb{Z}_5) = 5$. More generally, the char$(\mathbb{Z}_p)=p$ for each prime $p$. This formalizes into a theorem!

## Thm: Characteristic of a finite field is prime
The characteristic of a finite field $F$ is a prime. That is - $\text{char}(F)$ is prime. 

> If we consider for contradiction that char$(F) = m = a \cdot b$ for $k < a,b < m$. Then $m \cdot 1 = 0$ implies that $\gcd(a,b)\cdot 1 = 0 \rightarrow (a\cdot1)(b\cdot1)=0$. But this means that one of $a$ or $b$ is 0 since we're in an integral domain (no zero divisors), which contradicts to $m$ being the order of 1!


# Prop: Finite Field Implications (Linear)
Let $F$ be a finite field. We have the following observations:
1. There exists a prime $p$ such that char$(F)=p$.
2. $1 \in F$, $1+1=2 \in F$, $\ldots, p+1 \in F$. That is, $\mathbb{Z}_p$ (called a **prime field**) is a subset of $F$! Even stronger though, is that it's a **subfield** of $F$. 

Now, the next few are related: 

4. Addition - If $a,b \in F$, then $a+b \in F$.
5. Scalar multiplication - If $a \in F, \alpha \in \mathbb{Z}_p$, then $\alpha\cdot a \in F$. 

This means that **$F$ is a finite-dimensional vector space over $\mathbb{Z}_p$**!

6. From Linear Algebra, recall that if $V$ is an $n$-dimensional vector space over a field $K$, then $V \cong K^n$  (isomorphic to). 

## Corollary 
If $F$ is a finite field of characteristic $p$ prime, then $$|F| = p^n \text{   for some $n$.}$$

## Lemma: Fermat's Thm for Fields
Let $F$ be a field of size $|F|=q$ where $q = p^m$ (a prime power). Then, every element $$\beta \in F \quad\text{satisfies}\quad \beta^q = \beta.$$

From Abstract Algebra, Langrange's Theorem says that $\beta^{q-1}=1$ in $F/\{0\}$ since $|F/\{0\}|=q-1$.

## Lemma: Roots of Polynomials over a Field
If $p(x) \in F(x)$ of degree $n$, then $p(x)$ has at most $n$ roots (counting multiplicities) over field $F$.

# Thm: Combining Last two Lemmas
Let $F$ be a finite subfield of $E$ with $|F|=q$ where $q$ is a prime power. Then $\beta \in E$ is in $F \iff$ $$\beta^q = \beta.$$ 

## Corollary: Subfields Criterion
Consider $F_{p^m}, F_{p^n}$. Field $F_{p^m}$ is a subfield of $F_{p^n} \iff$
$$m \mid n.$$

# Def: Composite Field
Let $E, F$ be fields. Then, $E \cdot F$ is called the **composite field** of $E,F$ - the smallest field that contains both $E$ and $F$. 

> Examples; $\mathbb{F}_{2^3}$ and $\mathbb{F}_{2^4}$ Then, $\mathbb{F}_{2^3} \cdot \mathbb{F}_{2^4} = \mathbb{F}_{2^m}$. Since $m = \text{lcm}(3,4) = 12$ and $3 \mid m, 4 \mid m$. But this composite field is not a finite field because it lacks a prime power order. 

# Thm: Finite fields are unique
...Finite fields are unique. 

> To prove this, let $E,F$ be finite fields of size $q=p^m$. We will show that $E=F$. Taking the composite field $E \cdot F$ (may or not be finite), both $E,F$ are subfields of it. But since they are both of size $q$, by our corollary, $E = \{\alpha \in E \cdot F \mid \alpha^q = \alpha\}$. But the same corollary applies to $F$ as well - that is, $F = \{\alpha \in E \cdot F \mid \alpha^q = \alpha\}$. So $E=F$. 

**Some notation**: $q=p^m \rightarrow$ prime power is notated $\mathbb{F}_q$ or GF$(q)$ for the finite field of size $q$. 

The prime field is thus notated $\mathbb{F}_p = \mathbb{Z}_p$.  

> Let's construct $\mathbb{F}_8$. The characteristic is $2$ since $8=2^3$. We need an irreducible polynomial of degree 3 over $\mathbb{F}_2$. If $p(x) \in F(x)$ is of degree 2 or 3, then irreducible $\iff$ not having having any roots. 
> </n>
> Such an irreducible polynomial needs to be of the form $p(x) = x^3+ax^2+bx+1$. Specifically, the constant can't be 0 lest you allow factoring out $x$. So, there are four possibilities for $p(x)$ - the only two of these that isn't factorable is $a=1,b=0$ or vice versa. We get $x^3+x^2+1$ or $x^3+x+1$. Let's just pick the former. Then, $$\mathbb{F}_8 = \mathbb{F}_2[x]/\langle x^3+x^2+1 \rangle = \{a_0+a_1x+a_2x^2 \mid a_0,a_1,a_2 \in \mathbb{F}_2\}$$
> Replacing $x$ by $\alpha$, we have $\mathbb{F}_8 = \{a_0+a_1\alpha+a_2\alpha^2,\quad \alpha^3 = \alpha^2+1\}$.
> This looks like
> $$\begin{align*}
\mathbb{F}_8 &= \{0,1,\alpha,\alpha^2,1+\alpha, 1+\alpha^2, \alpha_+\alpha^2, 1+\alpha+\alpha^2\} \\
&= \{0,1,\alpha, \alpha^2, \alpha^3, \alpha^4, \alpha^5, \alpha^6\}
\end{align*}$$
Here, ![[Pasted image 20201103140046.png]]

---

# Thm: Fields -> Group Connection
$\mathbb{F}_q^* = \mathbb{F}_q/\{0\}$ is a cyclic group under multiplication. So, there exists a generator $\alpha \in \mathbb{F}_q$ such that 
$$\mathbb{F}_q = \{0,1,\alpha,\alpha^2,\ldots,\alpha^{q-2}\}.$$
Note that $\alpha^{q-1}=1$.

> Applied to the **Discrete Logarithm Problem (DLP) for finite fields**: Given $\beta \in \mathbb{F}_q$, find $n \in \mathbb{Z}_{\geq 0}$ such that $\beta = \alpha^n$ (with the convention that $0=\alpha^{-\infty}$). 

# Def: Zech's Log Table
Define primitive element $\alpha \in \mathbb{F}_q$. Then, assuming $\alpha$ is a root of an irreducible polynomial of degree $m$ over $\mathbb{F}_p$, then we can equivalently write

$$\mathbb{F}_q = \{0,1,\alpha,\alpha^2,\ldots,\alpha^{q-2}\} = \{a_0+a_1\alpha+\ldots+a_{m-1}\alpha^{m-1} \mid a_i \in \mathbb{F}_p\}$$

where again, $a_i$s are scalars/coefficients.

We can outline the following to illustrate this as a correspondence of the elements in two different forms: 

![[Pasted image 20201105130204.png]]

> Let's look at an example. Let's construct $\mathbb{F}_{16}$. Since $16=2^4$, we can write
> $$\mathbb{F}_{16} = \frac{\mathbb{F}_2[x]}{\langle p(x) \rangle}$$
> where $p(x)$ is irreducible over $\mathbb{F}_2$ and $\deg(p(x))=4$ in the form
> $$x^4+a_3x^3+a_2x^2+a_1x+a_0.$$
> In general, to construct $\mathbb{F}_{p^m}$, you need an irreducible polynomial over the prime field $\mathbb{F}_p$ of degree $m$. It needs to be 1) Monic and 2) All coeffs are either 0 or 1. 
> </n>
> So, our goal is to find a irreducible polynomial of degree 4 over $\mathbb{F}_2$ - so of the form shown above. Let's work our way up: Irreducibles of degree 1: $x,x+1$. Of degree 2: $x^2+x+1$. Of degree 3: $x^3+x^2+1, x^3+x+1$. For degree 4... 
> Reducible implies that it's a product of previous irreducibles! So, multiply those combinations that work out to degree 4 and eliminate them. 
> $$(x+1)^2(x^2+x+1),\quad (x+1)^4,\quad (x^2+x+1)^2,$$ $$(x+1)(x^3+x+1),\quad (x+1)(x^3+x^2+1)$$
> which multiply out to the following (remember we are in characteristic 2! Basically XOR):
> $$x^4+x^3+x+1,\quad x^4+1,\quad x^4+x^2+1,\quad x^4+x^3+x^2+1,\quad x^4+x^2+x+1.$$
> What's left? Three of them are thus irreducible: 
> $$x^4+x^3+x^2+x+1,\qquad x^4+x^3+1,\qquad x^4+x+1$$
> To construct our field, let's pick $x^4+x+1$ (remember, all are isomorphic to each other i.e. basically the same field).
> $$\begin{align*}
\mathbb{F}_{16} &= \frac{\mathbb{F}_2[x]}{\langle x^4+x+1 \rangle} \\
&= \{a_0+a_1\bar{x}+a_2\bar{x}^2+\bar{x}_3x^3 mid a_i \in \mathbb{F}_2\} \\
&\bar{x} \rightarrow \alpha \\
&= \{a_0+a_1\alpha + a_2\alpha^2 + a_3\alpha^3 \mid a_i \in \mathbb{F}_2, \alpha^4 = \alpha+1\}
\end{align*}$$
> So the set $\{1,\alpha,\alpha^2,\alpha^3\}$ is a **basis**. 
> Writing down Zech's log table for this field gives the following for all 16 elements: 
> ![[Pasted image 20201105132754.png]]

Now, let's try an example of an addition between two elements:

> $\alpha^5 + \alpha^{11}$. From the table, we see that this is $(\alpha+\alpha^2)+(\alpha^3+\alpha^2+\alpha) = \alpha^3$. How about $\alpha^5+\alpha^{12}$? We have $= \alpha+\alpha^2+\alpha^3+\alpha^2+\alpha+1= \alpha^3+1 = \alpha^{14}$.

Let's try multiplication: 

> $(\alpha^3+\alpha+1)(\alpha^3+\alpha+1) =\alpha^{10}\cdot \alpha^7 =\alpha^{17}=\alpha^2$ since $\alpha^{15}=1$. 

---

# Def: Minimal Polynomials 

Consider $\mathbb{F}_{p^m} = \mathbb{F}_{q}$. We know that $\alpha \in \mathbb{F}_{q}$ implies that $\alpha^2 = \alpha$. So, we can say every element in $\mathbb{F}_{q}$ is a root of $x^q-x$. That is,

$$x^q -x = (x-0)(x-1)(x-\alpha)(x-\alpha^2)\ldots(x-\alpha^{q-2}).$$

Notice that $x^q-x \in \mathbb{F}_{p}[x]$. We have that $x^q-x$ is a product of monic, irreducible polynomials! So, this means that every element in the field is a root of an irreducible polynomial over $\mathbb{F}_{p}$.

So, we can say a **minimal polynomial** of $\alpha^i$ is a monic irreducible polynomial of minimal degree over $\mathbb{F}_{p}$ that has $\alpha^i$ as a root. 

Some observations:
* The minimal polynomial of $\alpha^i$ is unique (and is irreducible). 
* Notice that if $f(x) \in \mathbb{F}_p[x]$, then $f(\alpha^p)=f(\alpha)^p$. (This comes from [[Modular Arithmetic and Congruence - 202008271246#^1be369 | freshman's dream]])

> As an example, remember that above we constructed $\mathbb{F}_{16} = \dfrac{\mathbb{F}_2[x]}{\langle x^4+x+1 \rangle}$ where $\alpha$ is our primitive element. A minimal polynomial of $\alpha$:
> $$(x+\alpha)(x+\alpha^3)(x+\alpha^4)(x+\alpha^8) = x^4+x+1$$
> Note that there's a LOT of steps in between to expand this, utilizing the table in the image above. 




# Related
[[Groups - 202009291317]]
[[Modular Arithmetic and Congruence - 202008271246]]