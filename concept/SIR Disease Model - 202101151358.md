# The SIR Model
#bioinformatics

## SI Model (building up)
A simple infectious disease model can be simply stated as the dynamics between the **susceptible** and **infected**. We can call the number of susceptible hosts $X(t)$ and the number of infected hosts as $Y(t)$ for some time $t$, where 
$$X+Y = N.$$

We can then define a set of coupled ODEs describing the change in these two sets of hosts: 
$$\begin{align*}
\frac{dX}{dt} &= \beta XY \\
\frac{dY}{dt} &= -\beta XY.
\end{align*}$$
Here, $\beta$ is the transmission rate. Since $\frac{dX}{dt},\frac{dY}{dt}$ has units of host/time, then $\beta$ has units $$\frac{1}{(\text{host} \cdot \text{time})}.$$
This parameter is what is known as a "black box" as it encompasses many different biological factors in one variable. That is, the product of the actual contact rate and the probability of infection given contact has occurred ($P(\text{infect}|\text{contact})$). 

This is thinking about the population in terms of sheer quantities, but a proportion model makes it a lot more intuitive. This is where $S,I$ come in, defined as 
$$S \equiv \frac{X}{N}, \qquad I \equiv \frac{Y}{N}.$$

## Frequency- vs. Density-Dependent Transmission
After some derivations, we can see that the definition of $\beta$ is dependent on the context, differentiated as $\hat{\beta}$ (see INF599 Lecture 2). With density-dependent, as the population increases, so does the infection rate. Frequency-Dependent does not have this distinction. In most cases of disease in humans, be it food-borne, sexual, etc., frequency is a more representative model. See below:

![[Pasted image 20210115142356.png]]

## Introduction to "Recovered" - SIR
The standard SI model works for some cases such as HIV, where infections last long and do not recover. For most diseases, however, a factor where a host can be removed from the system via life-long immunity is needed. This includes many diseases like chicken pox, where it's caught as a child, recovered from, and never caught again. The system then becomes the following: 

$$\begin{align*}
\frac{dS}{dt} &= \beta SI \\
\frac{dI}{dt} &= -\beta SI - \gamma I \\
\frac{dR}{dt} &= \gamma I
\end{align*}$$

where $\frac{1}{\gamma}$ is the average infection period of the chosen disease. There is a clear pipeline for how hosts move through this system, shown below:
![[Pasted image 20210115142931.png]]

The combination of these two parameters generalizes into the parameter $R_0$, which is the average number of secondary infections caused by the introduction of a single infectious individual into a naive host population. That is, at time $t=0$, then 
$$S(0) \approx 1, \qquad I(0) \text{  very low}.$$

For invasion to occur, we must have $R_0 > 1$, else the disease dies out. Many diseases' $R_0$ have been measured, including influenza (3-4), smallpox (3-6), and measles (16-18).

# Sources
INF 599 Lecture 2 (Joe M.)