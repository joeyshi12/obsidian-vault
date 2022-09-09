---
course: "cpsc313"
title: "Why Block-based File Systems?"
source: "P21.1"
---

## Recall: fixed-block
- Pick a block size that is a multiple of a sector
- All files are composed of multiple fixed-size blocks
- How much metadata is required? One disk address per block
- How much internal fragmentation is there? Depends on how large the block is
- Performance? Bad when blocks are scattered
- External fragmentation? NONE!
- **Problems? If files were large, the metadata could get big**

![[Pasted image 20220315144712.png]]

## Things to consider
POSIX creates files by writing bytes to them; they grow dynamically
- Extent-based allocation is not well-matched for this model
Some files are *sparse*. i.e., files have have holes in them/spaces in between bytes
- e.g., virtual machines may have large disk space that may never be used
- Extent-based files typically allocate disk space for the entire file