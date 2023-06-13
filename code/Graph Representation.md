## Adjacency List

Every vertex stores a list of adjacent vertices. In an undirected graph, an edge $(u, v)$ would be stored twice: once in vertex $u$ and again in vertex $v$.

An array or hash table of lists can store the adjacency list:
```
0: 1
1: 2
2: 0, 3
3: 2
```

However, it is often more preferred to use a class:
```python
class Graph:
    def __init__(self, nodes):
        self.nodes = nodes

class Node:
    def __init__(self, name, children):
        self.name = name
        self.children = children
```

## Adjacency Matrix

An adjacency matrix is an $N\times N$ boolean matrix, where $N$ is the number of nodes and a `true` value at $M_{ij}$ indicates an edge from $i$ to $j$. 

In an undirected graph, the adjacency matrix will be symmetric.

![[Pasted image 20220426143704.png]]