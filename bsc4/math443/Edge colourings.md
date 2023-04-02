---
course: MATH443
title: Edge colourings
chapter: 10.3
tags:
date: [[2023-03-29]]
---

A proper edge colouring of a graph $G$
is an assignment of colours to $E(G)$,
such that no pairs of adjacent edges are assigned the same colour.

The minimum number of colours needed for a proper edge-colouring
of a graph $G$ is called the **chromatic index** or **edge chromatic number** of $G$ denoted $\chi'(G)$.

A proper edge colouring using at most $k$ colours is a $k$-edge colouring.
Observation: $\chi'(G)\geq \Delta(G)$

## What is $\chi'(K_n)$?
Consider odd $n$. Then, $\|K_{n}\| = \frac{n(n-1)}{2} > \frac{(n-1)\Delta(K_n)}{2}$.
By [[Thm 10.13]], we have $\chi'(K_n) = \Delta(K_n) + 1 = n$.