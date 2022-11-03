---
course: CPSC317
title: Average Delay
topic:
tags:
module: 6
date: [[2022-11-02]]
---

$$\text{Avg Delay} = \frac{S}{1 - u}, \quad S := \text{Service time} = \frac{L}{R}, \quad u := \text{utilization/intensity}$$
Little's Law: $L = \lambda w$, $w := \text{Wait time}$
$$P(\pi i) = P(\text{\# people $= i$}) = (1 - u)u^{i}$$
$$\text{Ave Queue Utilization} = \sum P(\pi i)$$