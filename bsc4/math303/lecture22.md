Let $N(t)$ be a $\lambda$ rate Poisson process. What is the distribution of the arrival times given that $N(t) = n$.
i.e., $n$ events occur between $0$ and $t$.

![[lecture22 2023-03-10 13.04.46.excalidraw]]

Conditional density:
$$\begin{align*}
f(s_1,\dots, s_n | N(t) = n) &= \frac{f(s_1,\dots, s_n, N(t) = n)}{P(N(t) = n)} \\
&= \frac{\lambda^n e^{-\lambda s_n}\cdot e^{-\lambda(t - s_n)}}{/n!}
\end{align*}$$
## Order Statistics
Given $n$ random variables $Y_1,\dots, Y_n$,
reorder in ascending order $Y_{(1)}, Y_{(2)},\dots, Y_{(n)}$.
We call $Y_{(1)},\dots, Y_{(n)}$ is the **order statistics**.
If $Y_i$ are continuous and i.i.d.,
their joint density is
$f(y_1,\dots, y_n) = f(y_1)\cdots f(y_n)$

Now for any ascending sequence $y_1 < \cdots < y_n$, we have $Y_{(1)} = y_1,\dots, Y_{(n)} = y_n$.
iff there exists a permutation of $(1,\dots, n)$ $\sigma$, such that
$Y_{\sigma(1)} = y_1,\dots, Y_{\sigma(n)} = y_n$.

So, the joint density of the order statistics is $f(y_1,\dots, y_n) = n!f(y_1)\cdots f(y_n)$.

## Example
Suppose $Y_1,\dots, Y_n\sim Unif[0, t]$.
What is the joint density of the order statistics?

$f(y_i) = \frac{1}{t}$.
Then, $f(y_1,\dots, y_n) = \frac{n!}{t^n}$.

## Theorem
Let $N(t)$ be a Poisson process.
Conditioned on $N(t) = n$, the arrival times $S_1,\dots, S_n$
have the same distribution as the order statistics corresponding to
$n$ i.i.d, $Unif[0, t]$ random variables.