---
course: CPSC304
title: Relational Algebra Operations
tags:
module: 5
date: [[2022-10-13]]
---

## Selection
$\sigma_p(r) = \{t \mid p(t), t\in{r}\}$, where $p$ is a predicate
- e.g., Select all male moviestars: $\sigma_{\text{Gender = `Male'}}(\text{MovieStar})$

## Projection
$\pi_{A1, A2,\dots, Ak}(r)$ is the relation of $k$ attributes $A1, \dots, Ak$.
Duplicate rows are removed.

## Cartesian product
TODO

## Set difference
$r_1 - r_2$ tuples in $r_1$, but not in $r_2$

## Union
$r_1 \cup r_2$ tuples in $r_1$ and $r_2$

## Rename
$\rho(X, E)$ assigns relation $E$ to the label $X$
- e.g., $\rho(GenderlessStars(ID,Nom), \pi_{StarID,Name}(MovieStar))$

## Join
$R \Join_c S = \sigma_c(R\times S)$
A natural join $\Join$ joins by common attributes / same name attributes (order does not need to match)

## Division
$A(a, b) / B(b)$ is a new relation $Q(a)$,
where all tuples $t\in Q(a)$ occurs with every attribute in $B(b)$ in $A(a, b)$.
Note: we divide by the rightmost attributes in $A(a, b)$.