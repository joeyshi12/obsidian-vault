---
course: MATH443
title: Graph Definitions
tags: []
date: [[2023-01-09]]
---

## Definitions
- A **graph** is a pair $G = (V, E)$ of sets with $V$ nonempty and $E\subseteq\binom{V}{2}$.
    - $V$ is a **vertex set**. Generally asuume $V$ is finite.
    - $E$ is the **edge set**.
- The **order** of $G$ is $|G| = |V|$. We say graphs order 1 are trivial.
- The **size** of a graph is the number of edges $\|G\| = |E|$.
    - Typically, we use $n = |G|$ and $m = \|G\|$.
- Two vertices making an edge are its **endpoints**.
    - If edge $e$ has $x$ as its endpoint, $e$ and $x$ are incident.
- 2 vertices that share an edge are **adjacent** and are also called **neighbours** of one another.
    - The **neighbourhood** $N(x)$ is the set of all neighbours of $x$.
- The **degree** of a vertex $x$ is its number of neighbours $\text{deg}(x) = |N(x)|$
