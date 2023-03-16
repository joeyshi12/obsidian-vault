---
title: Chapter 9 Planarity
tags: planarity
date: [[2023-03-13]]
---

# Planarity

## 9.1: Planar Graphs

## 3 houses, 3 utility problems.
Want pipe from each utility to each house, can't cross

![[Chapter 9 Planarity 2023-03-13 15.01.49.excalidraw]]

A graph is called **planar** if $G$ can be drawn in the plane
so that none of its edges cross each other
(and an edge can't be drawn through a vertex not on it).
Otherwise, $G$ is nonplanar.

Planar graphs include trees, paths, cycles.
Subgraphs of planar graphs are planar.
A plane graph divides the plane into maximal connected pieces
called **regions** or **faces**.
In every plane graph, there is always an unbounded face (exterior region)

![[Chapter 9 Planarity 2023-03-13 15.09.19.excalidraw]]

Rigorouse proofs of some foundational observations involve topology
(eg Jordon curve theorem) which is beyond the scope of the course.
We will make some observations without proof.

## Observations
1. If $G$ is a plane graph with $\geq 2$ regions, then the boundary of every region of $G$ has a cycle as a subgraph.
2. A bridge is always on the boundary of exactly 1 region. A non bridge is always on the boundary of exactly 2 regions.
3. If $G$ is a connected plane graph with $\geq 3$ edges, then the boundary of every region of $G$ has $\geq 3$ edges.
    - If $G$ has $1$ region, $G$ is the boundary of that region and $\|G\|\geq 3$.
    - If $G$ has multiple regions, each region has a cycle on its boundary.
4. Let $R$ be the boundary of a region in a plane graph $G$. Then, there is a plane drawing of $G$, such that $R$ is the boundary of the exterior.