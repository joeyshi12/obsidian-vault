```python
class Node:
    def __init__(self, data, next_node=None):
        self.data = data
        self.next_node = next_node

    def append(data):
        curr = self
        while curr.next_node:
            curr = curr.next_node
        curr.next_node = Node(data)
```