## Korsaraju's Algorithm

1. Let $S$ be a stack of all vertices in post DFS order
2. Pop vertices from S one by one. For each popped vertex $v$, run DFS from $v$ and set the representative vertex for each vertex traversed to $v$.

![[korsaraju_algorithm.svg]]