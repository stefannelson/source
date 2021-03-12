# Def: Euler $\phi$ Function
#math/numbertheory 

Of course, the main question is what is $k$?  
$$ \phi(n) = |\{1 \leq a \leq n | (a,n) = 1\}|$$ 

This is a number theoretical function that can be found for small $n$. 

> Examples: $\phi(1) = 1, \phi(2) = 1, \phi(3) = 2, \phi(4)=2, \phi(5)=4, \phi(6)=2, \phi(7)=6, \phi(8)=4$.
> We can observe from this that $\phi$ is not a monotone function. It increase and decreases all the time. Additionally, for primes, $\phi(p) = p-1$ since every number below $p$ is relatively prime to it! 

> Now, what about $\phi(p^n)$. Notice that 
> $$\phi(p^n) = | \{ a: 1 \leq a \leq p^n | \gcd(a,p^n) =1 \} |$$ 
> We're trying to find $a$'s such that $p \cancel{\mid} a$, which is $\boxed{p^np^{n-1}} = p^{n-1}(p-1)$.

## Lemma: Multiplicative Property of $\phi$
$\phi$ is multiplicative - that is, 
$$\phi(mn) = \phi(m)\phi(n) \qquad \forall m,n: \gcd(m,n) = 1.$$

> What does this imply? By FTA, a number can be written as a product of primes of various amounts. This means that we can take these primes out, saying $\phi(n) = \phi(p)\phi(\frac{n}{p})$ and expand that until we run out of primes.
> $$\phi(n) = (p^{\alpha_1}_1 , p_1^{\alpha_1-1})\ldots(p^{\alpha_k}_k , p_k^{\alpha_k-1})$$ 
> $$\vdots$$
> $$n(1-\frac{1}{p_1})\ldots(1-\frac{1}{p_k})$$
> It only relies on the prime factors of $n$, **not** the prime factorization. 

Let's look at a specific example:

> Ex: $\phi(48) = 48(1 - \frac{1}{2})(1 - \frac{1}{3}) = 16.$

Now, let's observe that if we have the RSRC $\{ a_1, a_2, \ldots, a_{\phi(n)}\}$. If we assume $m$ is an integer with $(m,n) = 1$, then
$$\{ ma_1, ma_2 , \ldots ma_{\phi(n)}\}$$ is also a RSRC. 


# Thm: Euler's Congruence Theorem
Let $m>1, (a,m)=1$. Let $\{x_1, x_2, \ldots, x_{\phi(m)} \}$. By a previous observation,  $\{ax_1, ax_2, \ldots, ax_{\phi(m)} \}$ is a RSRC mod $m$. So,
$$(ax_1)(ax_2) \ldots (ax_{\phi(m)}) \equiv x_1x_2\ldots x_{\phi(m)} \bmod{m}.$$

After cancelling, we get that 

$$\boxed{a^{\phi(m)} \equiv 1 \bmod{m}.}$$

This is powerful because it's not just for primes, it's for everything! It turns out Fermat's Little Theorem is a special case of this. 

> Example: Find the last 2 digits of $13^{22}$. 
> So, we're basically trying to find $x \equiv 13^{22} \bmod{100}$. Like the Chinese Remainder Theorem, we're trying to solve 
> $$\begin{align*}
x &\equiv 13^{22} \bmod{4} \rightarrow x \equiv 1 \bmod{4} \\
x &\equiv 13^{22} \bmod{25} 
\end{align*}$$
> Now, we can use $13^{22} = 13^2 \cdot 13^{20} \equiv 13^2 \bmod{25} \equiv 19 \bmod{25}$.  We can use $x = 19, 19 +25, 19+50$. This last one is equivalent to 1 mod 4. So $13^22 \equiv 69 \bmod{100}.$

# Applications to Cryptography
1. **3 Pass Protocol**. Alice sends encrypted "box" to Bob, Bob sends it back encrypted with his own lock. Alice undoes her encryption, sends it back. Bob undoes his lock - ta da!

> In terms of Number Theory, this works via the Discrete Log Problem as well as Euler's Congruence Theorem. Specifically,
> Given large public number $n$, Alice sends Bob message $m$ with $m^e \bmod n$, where $(e, \phi(n)) = 1$. Not knowing what $e$ is creates the security. Then, Bob receives it, and sends back to Alice with $d$ such that $(d, \phi(n))=1$ and sends $(m^e)^d$ to Alice. 
> Alice can find $e^{-1} \bmod \phi(n)$, which exists from what we learned above, then calculates $((m^e)^d)^{e^{-1}} \bmod n$, which is congruent to $m^d \bmod n$ by Euler's Congruence Theorem. After sending back to Bob, it's in terms of what Bob knows, but not any interceptors! Specifically, Bob finds $d^{-1}$ which in turn recovers the message. 
 
2. **RSA**. Basically, Euler's Congruence Theorem... again. 
> Take two large primes $p,q$ very large. Then $N = pq$ is public and $e$, the encryption exponent, is chosen such that $(e,\phi(N))=1$.  So the public key is $(N,e)$. and $(p,q,d)$ is the private key, where $d=e^{-1} \bmod \phi(N)$. Remember, $$\phi(N) = (p-1)(q-1).$$ 
> To decrypt, calculate $(m^e)^d \bmod N$. 


---

>Alternatively, Given $\gcd(m,a)=1$ (coprime) then $\Phi(m)$ is the Euler coefficient of $m$. If $m = p \cdot q$ with $p, q$ primes: 
>$$\Phi_m = (p-1)(q-1), a \in \{X_1, X_2, \ldots, X_{\Phi m}\}$$
>So $a^{\Phi m} \equiv 1 \mod m$.

# Related
[[Modular Arithmetic and Congruence - 202008271246]]