---
lecture: 24
tags:
date: [[2023-03-13]]
---

## Poisson Thinning
- $N(t)$ is a $\lambda$ rate Poisson process
- Each occurrence is independetly classified as one of $k$ types.
    - Classified as Type $i$ with probability $p_i$ $i = 1,\dots, k$
- Let $N_i(t)$ be the number of occurrences of Type $i$ by time $t$.

Then, $N_i(t)$ are independent Poisson processes of rate $\lambda_i = p_i\lambda$.

Q: What if the classification probabilities depend on time?

## Proposition
$N_1,\dots, N_k$ are independent Poisson random variables with rates $\lambda_i$
with $E[N_i(t)] = \lambda\int_{0}^{t} p_i(s) ds$.

## Example: Estimating infected population

Model:
- Individuals contract some virus as a rate $\lambda$ Poisson process, $\lambda$ unknown
- The time from infection to onset of symptons is random with known CDF $F(s) := P(\text{symptoms show within time s of infection})$
- For some $t > 0$, let
    - $N_1(t) =$ \# of individuals who have shown symptoms
    - $N_2(t) =$ \# of individuals who are infected but haven't shown symptoms
- You observe $N_1(t)$ at one time point
- Goal: estimate $\lambda$ and $N_2(t)$ 

Occurrence: an individual is infected
Type 1: individual show symptoms at time $t$
Type 2: individual shows no symptom at $t$
$p_1(s) = P(\text{showing symptoms in time} \leq t - s) = F(t - s)$
$p_2(s) = 1 - F(t - s)$

$$E[N_1(t)]
= \lambda\int_{0}^{t} p_1(s) ds
= \lambda\int_{0}^{t} F(t - s) ds$$
Estimate $\lambda$: $$\hat{\lambda} = \frac{\hat{N_1(t)}}{\int_{0}^{t} F(t - s) ds}$$
Similarly,
$$\hat{E[N_2(t)]}
= \hat{\lambda}(t - \int_{0}^{t} F(t - s)) ds
= \hat{N_1}()$$