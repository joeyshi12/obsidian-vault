---
course: CPSC304
title: Data Cube
topic:
tags:
module: 8
date: [[2022-11-29]]
---

## Data Cube
- $k$-dimensional object containing fact data for each dimension
- Each cells contain a measure group, which consists of one or more numeric measures.
    - These are facts (or aggregated facts)

![[Pasted image 20221129155931.png|600]]

## Estimating size
- $m$ models, $c$ colours, $y$ years $\Rightarrow\text{CubeSize} = (m + 1)(c + 1)(y + 1)$
- For a $k$-dimensional cube, we need $2^{k}$ group by operations.