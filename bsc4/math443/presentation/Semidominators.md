## DFS

Starting from the root,
move to the leftmost unvisited vertex until we
reach a vertex with no edge to an unvisited vertex.
Then, backtrack to the closest ancestor with
and edge to an unvisited vertex and repeat.
Continue until all vertices are visited.

# Semidominators
$sdom(w) = \min\{v \mid \exists v_0v_1\dots v_n, v_0 = v, v_n = w, v_i > w, 0 < i < n\}$
Earliest visited vertex with a path to w with interior vertices visited after w.

Examples
- Don't list vertices
- "Semidominator path"
- The only path to F from R is on the left, but the interior vertices are not always smaller.