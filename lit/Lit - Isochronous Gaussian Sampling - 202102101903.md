# Isochronous Gaussian Sampling: From Inception to Implementation With Applications to the Falcon Signature Scheme
#math/cryptography/falcon
> @inbook{Howe\_Prest\_Ricosset\_Rossi\_2020, place={Cham}, series={Lecture Notes in Computer Science}, title={Isochronous Gaussian Sampling: From Inception to Implementation: With Applications to the Falcon Signature Scheme}, volume={12100}, ISBN={978-3-030-44222-4}, url={[http://link.springer.com/10.1007/978-3-030-44223-1\_4](http://link.springer.com/10.1007/978-3-030-44223-1_4)}, DOI={[10.1007/978-3-030-44223-1\_4](https://doi.org/10.1007/978-3-030-44223-1_4)}, abstractNote={Gaussian sampling over the integers is a crucial tool in lattice-based cryptography, but has proven over the recent years to be surprisingly challenging to perform in a generic, eﬃcient and provable secure manner. In this work, we present a modular framework for generating discrete Gaussians with arbitrary center and standard deviation. Our framework is extremely simple, and it is precisely this simplicity that allowed us to make it easy to implement, provably secure, portable, eﬃcient, and provably resistant against timing attacks. Our sampler is a good candidate for any trapdoor sampling and it is actually the one that has been recently implemented in the Falcon signature scheme. Our second contribution aims at systematizing the detection of implementation errors in Gaussian samplers. We provide a statistical testing suite for discrete Gaussians called SAGA (Statistically Acceptable GAussian). In a nutshell, our two contributions take a step towards trustable and robust Gaussian sampling real-world implementations.}, booktitle={Post-Quantum Cryptography}, publisher={Springer International Publishing}, author={Howe, James and Prest, Thomas and Ricosset, Thomas and Rossi, Mélissa}, editor={Ding, Jintai and Tillich, Jean-Pierre}, year={2020}, pages={53–71}, collection={Lecture Notes in Computer Science} }

[[Howe et al. - 2020 - Isochronous Gaussian Sampling From Inception to I.pdf]]

This paper addresses the issue of easily and securely sampling integers over a normal/Gaussian distribution, which is vital for the implementation of systems such as Falcon - named **SAGA**.  This is statistically isochronous - that is: 

> We say that $\mathcal{A}$ is statistically isochronous with respect to $\mathcal{S}$ is there exists a distribution $\mathcal{D}$ independent of all variables in $\mathcal{S}$, such that the running time of $\mathcal{A}$ is statistically close (for a clearly identified divergence) to $\mathcal{D}$. 

We also define the Gaussian distribution $D$ via first the Gaussian function over $\mathbb{R}$ as $\rho_{\sigma,\mu}$ for $\sigma, \mu \in \mathbb{R}, \sigma > 0$. Here:
$$\rho_{\sigma,\mu}(x) = \exp\left( -\frac{(x-\mu)^2}{2\sigma^2} \right).$$
Then, for some countable set $S \subseteq \mathbb{R}$, our Gaussian distribution over $S$ is defined 
$$D_{S,\sigma,\mu}(z) = \rho_{\sigma, \mu}(z)/\rho{\sigma, \mu}(S).$$

The algorithms are as follows:
![[Pasted image 20210211111248.png]]

Practically, the two internal functions used in these two algorithms can only be approximated. Specifically, **BaseSampler** $\approx D_{\mathbb{Z}+, \sigma_{max}}$ and ApproxExp $\approx exp$. BaseSampler is some algorithm that samples an element from the fixed Gaussian distribution $D_{\mathbb{Z}+,\sigma_{max}}$ Conditions can be set to make these indistinguishable from $D_{\mathbb{Z},\sigma,\mu}$ for arbitrary mean $\mu \in [0,1]$ (notation-wise, not having $\mu$ listed is assumed zero) and $\sigma_{min} \leq \sigma \leq \sigma_{max}$. 

# Related
[[Lit - How to Use a Short Basis Trapdoors for Hard Lattices and New Cryptographic Constructions - 202102101906]]
[[Lit - Falcon Fast-Fourier Lattice-based Compact Signatures over NTRU Specification v12 - 202102101900]]
[[Lit - Fast Fourier Orthogonalization - 202102101933]]