# Theorem 6.9
If $f$ is monotone on $[a, b]$ and if $\alpha$ is continuous on $[a, b]$, then $f\in\mathcal{R}_{\alpha}[a, b]$.

## Proof

Given $n\in\mathbb{N}$, we can choose $P$, such that
$$\Delta \alpha_i = \frac{\alpha(b) - \alpha(a)}{n}$$
by the intermediate value theorem.
![[Pasted image 20220114090851.png]]

Then $U(P) - L(P) = \sum_{i=1}^{n} (M_i - m_i)\Delta \alpha_i = \frac{\alpha(b) - \alpha(a)}{n} \sum_{i=1}^{n}(M_i - m_i)$.
Suppose f is increasing.
Then, $M_i - m_i = f(x_i) - f(x_{i-1})$.
So, 
$$U(P) - L(P) = \frac{\alpha(b) - \alpha(a)}{n} \sum_{i=1}^{n} f(x_i) - f(x_{i-1})
= \frac{\alpha(b) - \alpha(a)}{n} [f(b) - f(a)$$

Given $\epsilon > 0$, we can choose n (and hence P) s.t. $U(P) - L(P) < \epsilon$, so $f\in\mathcal{R}_{\alpha}[a, b]$ by theorem 6.6.