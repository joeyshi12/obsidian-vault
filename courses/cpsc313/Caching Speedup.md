---
topic: "Caching Speedup"
---

We define **speed up** to be
$$S = \frac{t_{old}}{t_{new}}$$
*Example:* 20% faster
$$t_{new} = 0.8t_{old} \Rightarrow S = \frac{1}{0.8} = 1.25$$

Amdahl's law: suppose a portion of a program $\alpha$ is $k$ times faster.
Then,
$$t_{new} = t_{old}((1 - \alpha) + \frac{\alpha}{k})$$
Thus,
$$S = \frac{1}{1 - \alpha + \frac{\alpha}{k}}$$
*note:* $\alpha$ differs between different programs, but $k$ is consistent