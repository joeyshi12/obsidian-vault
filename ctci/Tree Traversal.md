## In-order
Visit left branch, then current node, then right branch

```python
def in_order(node):
    if node:
        in_order(node.left)
        visit(node)
        in_order(node.right)
```

## Pre-order
Visit current node before its child nodes

```python
def pre_order(node):
    if node:
        visit(node)
        pre_order(node.left)
        pre_order(node.right)
```

## Post-order
Visit child nodes before the current node

```python
def post_order(node):
    if node:
        post_order(node.left)
        post_order(node.right)
        visit(node)
```