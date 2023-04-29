# Graph Search

![[Pasted image 20220426143927.png]]

## Depth-First Search (DFS)

```python
def search(root):
    if not root:
        return
    else:
        visit(root)
        root.visited = True
        for node in root.adjacent:
            if not node.visited:
                search(node)
```

## Breadth-First Search (BFS)

```python
from collections import deque

def search(root):
    queue = deque() # using a stack instead will turn this into DFS
    root.visited = True
    queue.append(root)

    while queue:
        p = queue.popleft()
        visit(p)
        for node in p.adjacent:
            if not node.visited:
                node.visited = True 
                queue.append(node)
```

## Bidirectional Search

Used to find the shortest path between source and destination node by running 2 simultaneous BFS from each node.

![[Pasted image 20220426145628.png]]

