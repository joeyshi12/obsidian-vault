```python
if y {  
  x <- 1  
} else {  
  x <- 2  
}  
z <- x + 1
```

![[Pasted image 20230328160406.png]]

```python
if y {  
  x_1 <- 1  
} else {  
  x_2 <- 2  
}
# x_3 <- x_??? + 1
x_3 <- phi(x_1, x_2)
```

How do we determine in general,
where to place the joins??

```python
if y_1 {  
  if y_2 {  
    x <- 1
  } else {  
    if y_3 {  
      x <- 2  
    } else {  
      x <- 3  
    }  
  }
} else {  
  x <- 4  
}  
z <- x + 1
```

## Definition
The dominance frontier of a vertex $v$
is the set of vertices $S$,
such that $v$ does not dominate $S$
and $v$ dominates an immediate predecessor of $Y$

If node $v$ contains an assignment to a variable $x$, then put $\phi$ for $x$ in the dominance frontier of $v$.

```python
if y_1 {  
  if y_2 {  
    x_1 <- 1
  } else {  
    if y_3 {  
      x_2 <- 2  
    } else {  
      x_3 <- 3  
    }
    
    z_1 <- phi(x_2, x_3)
  }
  z_2 <- phi(x_1, z_1)
} else {  
  x_4 <- 4
}
z_3 <- phi(z_2, x_4) + 1
```

![[preview 2023-03-28 16.22.13.excalidraw|800]]