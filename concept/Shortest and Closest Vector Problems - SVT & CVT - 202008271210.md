# Shortest/Closest Vector Problem
 #math/cryptography 

## Description 
In Lattice-Based Cryptography, the **Shortest Vector Problem requires finding a grid point that is as close as possible to the origin of a long basis**.

On the other hand, the **Closest Vector Problem requires finding a grid point as close as possible to another given grid point**. 

In these [[NTRU Lattices - 202008281320]], a basis can be defined a small amount of vectors. With this set, any point in the lattice can be reached through a mix of picking whole numbers and applying operations to those vectors. 

We can describe this shortest vector for a given lattice $\mathcal{L}$ as:
$$\lambda_1(\mathcal{L}) = \inf\{r \mid \dim(\text{span}(\mathcal{L} \cap B(0,r))) \geq i\}$$ 

where $B(0,r)$ is the closed ball of radius $r$ around the origin $0$. Remember that a linearly independent set of vectors adds a new dimension for every new vector we consider!

> Essentially, $\lambda(\mathcal{L})$ will be the smallest possible value in a set of all r where a closed ball of radius r at the origin contains at least i linearly independent lattice points.

![[Pasted image 20201030120112.png]]


## Why is it Difficult? 

The reason finding a grid point close to the origin is hard is that long vectors are hard to manipulate into becoming smaller vectors, especially when you deviate from 2D. If there are 10,000 dimensions, the vector that you need to find suddenly requires 10,000 coordinates. All of these coordinates need to be manipulated by long vectors to be become small simultaneously. 

## How do you Make Public/Private Keys?
For SVT applications in cryptography, the gist is to create two bases that generate the same lattice - one long (public key), and one short (private key). The short basis makes it easy to find the shortest and/or closest vector in a lattice. That said, the long basis can still verify that a vector is short/close enough, making for a solid trapdoor mechanism that quantum computers still struggle with in higher dimensions. 



# Sources
Wickr. â€œWhat Is Lattice-Based Cryptography & Why You Should Care.â€ Medium, August 15, 2020. https://medium.com/cryptoblog/what-is-lattice-based-cryptography-why-should-you-care-dbf9957ab717.

Zahid, Ahsan Z. Lattices, Cryptography, and NTRU. p. 26.
