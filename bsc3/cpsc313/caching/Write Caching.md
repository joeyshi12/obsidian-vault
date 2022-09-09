## Terminology
- **Write-through**: write to both cache and memory
- **Write-back**: write to cache and write to memory only when we evict the element from the cache
- **Write-allocate**: on a miss, allocate a slot in the cache for the missed cache line

![[Pasted image 20220321223755.png|700]]

## Write-back
- **Write hit**: write to cache and set the dirty bit if necessary
- **Write miss**
    - **No write allocate**: write to data source
        - $\overline{t} = \alpha t_{cache} + (1 - \alpha) t_{source}$
    - **Write allocate** (Common): read data from source into cache and then write to cache and *sometimes* to the data source. (always set the dirty bit!)
        - $\overline{t} = \alpha t_{cache} + (1 - \alpha) t_{source}(\gamma + 2(1 - \gamma))$
        - hit rate = $\alpha$
        - clean rate = $\gamma$
        - When the cache line is clean, we sometimes include the time to read data from the source AND to update the cache, so
            - $\overline{t} = \alpha t_{cache} + (1 - \alpha) (\gamma (t_{source} + t_{cache}) + 2(1 - \gamma) t_{source})$

## Write-through
- **Write hit**: write to cache, update dirty bit, and write to data source (cache write & data source write can be done in parallel)
- **Write miss**:
    - **No write allocate**: write to data source
        - $\overline{t} = t_{source}$

| Hit/Miss | .                               |
| -------- | ------------------------------- |
| Hit      | W.T. (D.S.)                     |
|          | W.B. (C)                        |
| Miss     | W.T. (D.S.)                     |
|          | W.B. clean (D.S.)               | 
|          | W.B. evict dirty line (D.S.)\*2 |
