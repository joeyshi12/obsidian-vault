---
course: "cpsc320"
topics: ["DP"]
---


# Longest Common Subsequence
The longest common subsequence of 2 strings $A$, $B$ is the longest string whose letters appear in order (not necessarily consequtive) within both A and B.
For example, the $LCS$ of "computer science" and "mathematics" is "mteic".


## Test Cases
```python
# Trivial
LCS("", "") == ""
LCS("a", "") == ""
LCS("", "a") == ""
LCS("a", "b") == ""
LCS("a", "a") == "a"

# Non-trivial
LCS("abcd", "bcde") == "bcd"
LCS("abcd", "bde") == "bd"
```


## Length of LCS
Let $LLCS$ be the length of the longest common subsequence between $A$ and $B$.
Consider the strings "tycoon" and "country". Removing the last letter of "country" does not change the $LLCS$ of the 2 strings.
If removing "y" from country did affect the $LLCS$, then "y" must belong to the LCS, which is only possible if $LCS$ = "y".
This is a contradiction since "con" is a larger common subsequence.

```python
LLCS("tycoon", "countr") == LLCS("tycoon", "country")
```

Consider "compute" and "science". 
$LLCS(\text{``compute"}, \text{``science"}) = 1 + LLCS(\text{``comput"}, \text{``scienc"})$ since "e" is the last character in both strings.

**General Recurrance Relation**
$$
LLCS(A[1..n], B[1..m]) = \begin{cases}
0 & n = 0 \text{ or } m = 0 \\
1 + LLCS(A[1..n-1], B[1..m-1]) & A[n] = B[m] \\
\max(LLCS(A[1..n-1], B[1..m]), LLCS(A[1..n], B[1..m-1])) & \text{otherwise} \\
\end{cases}
$$

```python
def LLCS(A: str, B: str) -> int:
    cache = [[-1] * len(B) for _ in enumerate(A)]
    return __LLCS(A, B, len(A) - 1, len(B) - 1, cache)

def __LLCS(A: str, B: str, i: int, j: int, cache: List[List[int]]) -> int:
    if i < 0 or j < 0:
        return 0
    if cache[i][j] < 0:
        if A[i] == B[j]:
            cache[i][j] = 1 + __LLCS(A, B, i - 1, j - 1, cache)
        else:
            cache[i][j] = max(
                __LLCS(A, B, i - 1, j, cache),
                __LLCS(A, B, i, j - 1, cache)
            )
    return cache[i][j]
```

```
          | * | c | co | cou | coun | count | countr | country |
   -------+---+---+----+-----+------+-------+--------+---------+
   *      | 0 | 0 |  0 |  0  |  0   |   0   |   0    |    0    |
   -------+---+---+----+-----+------+-------+--------+---------+
   t      | 0 | 0 |  0 |  0  |  0   |   1   |   1    |    1    |
   -------+---+---+----+-----+------+-------+--------+---------+
   ty     |*0*| 0 |  0 |  0  |  0   |   1   |   1    |    2    |
   -------+---+---+----+-----+------+-------+--------+---------+
   tyc    | 0 |*1*|  1 |  1  |  1   |   1   |   1    |    2    |
   -------+---+---+----+-----+------+-------+--------+---------+
   tyco   | 0 | 1 | *2*| *2* |  2   |   2   |   2    |    2    |
   -------+---+---+----+-----+------+-------+--------+---------+
   tycoo  | 0 | 1 |  2 | *2* |  2   |   2   |   2    |    2    |
   -------+---+---+----+-----+------+-------+--------+---------+
   tycoon | 0 | 1 |  2 |  3  | *3*  |  *3*  |  *3*   |   *3*   |
   -------+---+---+----+-----+------+-------+--------+---------+
```


## LCS Algorithm
1. Start from index $(n, m)$
2. Traverse the table and construct the $LCS$
    - Move to $(n - 1, m - 1)$ if $A[i] = B[j]$ and include the character in the final solution
    - Otherwise, move to either $(i - 1, j)$ or $(i, j - 1)$ depending on which index maximizes $LLCS$.
3. Repeat

```python
def LCS(A: str, B: str) -> str:
    cache = [[-1] * len(B) for _ in enumerate(A)]
    length = __LLCS(A, B, len(A) - 1, len(B) - 1, cache)

    if length == 0:
        return ""

    subsequence = [""] * length
    curr = LLCS - 1
    i, j = len(A) - 1, len(B) - 1
    while curr >= 0:
        if A[i] == B[j]:
            subsequence[curr] = A[i]
            i -= 1
            j -= 1
            curr -= 1
        elif cache[i - 1][j] > cache[i][j - 1]:
            i -= 1
        else:
            j -= 1
    return "".join(subsequence)
```

- Time-complexity: $O(nm)$
- Space-complexity: $O(nm)$


## DP Approach to LLCS
```python
def LLCS(A: str, B: str) -> int:
    cache = [[0] * (len(B) + 1) for _ in range(len(A) + 1)]
    for i, c1 in enumerate(A):
        for j, c2 in enumerate(B):
            if c1 == c2:
                cache[i + 1][j + 1] = 1 + cache[i][j]
            else:
                cache[i + 1][j + 1] = max(cache[i][j + 1], cache[i + 1][j])
    return cache[-1][-1]
```

**note**: $O(n)$ is enough if we're only concerned with computing $LLCS$.