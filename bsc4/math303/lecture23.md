---
course: MATH303
lecture: 23
tags:
date: [[2023-03-13]]
---

## Queuing Systems
Consider a 3-server system in which a customer is served first by Server 1,
then by Server 2, then by Server 3, and then departs.
The service times at Server $i$ are exponential random variables
with rates $\mu_i$, $i = 1,2,3$.

1. Suppose that when you arrive, there is no one in the system. What is the expected time until you leave Server $3$?

$T_i$ is the time to be server by Server $i$.
$E(T_1 + T_2 + T_3) = \frac{1}{\mu_1} + \frac{1}{\mu_2} + \frac{1}{\mu_3}$

2. Suppose that when you arrive, you find $5$ customers at Server $2$. What is the probability that at least 1 is still in Server $2$ when you get to server $2$.

$P(\text{one customer finishes before you arrive}) = \frac{\mu_2}{\mu_1 + \mu_2}$
$1 - P(\text{No one is at server 2 when you arrive}) = 1 - \left(\frac{\mu_2}{\mu_1 + \mu_2}\right)^5$

## Question 2
Let $N(T)$ be a $\lambda$ rate Poisson process.
Let $T_1, T_2,\dots$ be interarrival times (time between arrivals).

1. What is $E[N(t + s) | N(t) = k]$?

$$\begin{align*}
E[N(T) + N(t + s) - N(t) | N(t) = k] &= E[N(t) | N(t) = k] \\
&= E[N(t + s) - N(t) | N(t) = k] \\
&= k + E[N(t + s) - N(t)] \\
&= k + E[Poisson(\lambda s)] \\
&= k + \lambda s
\end{align*}$$
## Problem 2
Q: What is $E[N(t) | N(t+s) = k]$?
Recall: Conditional distribution of arrival times is uniform

Consider $t_i$ = Time of event among the $k$ occurring between $0$ and $t + s$ ($i\leq i\leq k$).
$t_i\sim Uniform[0, t+s]$
$$E[\text{\# of events }i | t_i\in [0, t]]
= E[\sum_{i=1}^{k} \mathbb{1}_{u_i\in{[0, t]}}]
= \sum_{i=1}^{k} P(u_i\in{[0, 1]})
= \sum_{i=1}^{k} \frac{t}{t + s}$$

## Problem 3
Q: What is $E[T_1 | N(t) = k]$? ($T_1$ = Time of first event)

$U_i\sim Uniform [0, t]$.
$$E[T_1 | N(t) = k] = E[\min(U_1,\dots, U_k)]$$
Take the c.d.f. of $Z = \min(U_1,\dots, U_k)$.
$$\begin{align*}
P(Z\geq s) &= P(U_1\geq s,\dots, U_k\geq s) \\
&= (P(U_1\geq s))^k \\
&= \left(\frac{t-s}{t}\right)^k
\end{align*}$$
Evaluate the following integral as an exercise to get the final answer.
$$E[Z] = \int_{0}^{\infty} P(Z\geq s) ds = \frac{t}{k + 1}$$

## Problem 4
Q: What is $E[T_1 | N(2) - N(1) = 2]$?

Consider 2 cases:
1. 0 events between 0 and 1
2. More than 0 events between 0 and 1

$$\begin{align*}
E[T_1 | N(2) - N(1) = 2]
&= E[T_1 | N(2) - N(1) = 2, T_1 < 1]P(T_1 < 1 | N(2) - N(1) = 2) &[I] \\
&+E[T_1 | N(2) - N(1) = 2, T_1\geq 1]P(T_1\geq 1 | N(2) - N(1) = 2) &[II]
\end{align*}$$

$II \Rightarrow T_1\sim 1 + \min(U_1, U_2)$, $U_i\sim Uniform [0, 1]$. So, 
$$\begin{align*}
II &= E[1 + \min(U_1, U_2)]P(T_1\geq 1) \\
&= (1 + \frac{1}{3})P(T_1\geq 1) &[\text{From 3}]
\end{align*}$$

$$I = E[T_1\cdot \mathbb{1}_{(T_1 < 1)}]P(T_1 < 1)
= \int_{0}^{1}\lambda e^{-\lambda s}ds \cdot P(T_1 < 1)$$
and finally $P(T_1\geq 1) = 1 - P(T_1 < 1) = 1 - e^{-1}$.