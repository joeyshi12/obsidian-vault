## Rank

The rank of a matrix $A\in{\text{R}^{m\times n}}$ is  $\text{rank}(A) = \text{dim}(\text{image}(A))$.
A matrix is said to have full rank if $\text{rank}(A) = \min(m, n)$.
I.e., either the rows are linearly independent or the columns are linearly independent

## Positive Definite Matrix

$A$ is positive definite if $x^TAx > 0$ for any column vector $x$.
$A$ is positive semi-definite if $x^TAx \geq 0$ for any column vector $x$.
Otherwise, $A$ is indefinite.

All of the following statements are equivalent:
- $A$ is positive definite
- $A$ is congruent with a diagonal matrix with positive real entries
- $A$ is symmetric or Hermitian and all its eigenvalues are real and positive
- $A$ is symmetric or Hermitian and all its leading principal minors are positive
- $A = B^TB$ for some invertible matrix $B$