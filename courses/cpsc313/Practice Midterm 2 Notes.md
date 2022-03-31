## R5.2
TRUE
- If two different processes open the same file, the file descriptors returned will map to different open file table entry
- If two different processes open the same file, the file descriptors returned will map to the same vnode table entry
- If two threads in the same process open the same file, the file descriptors returned will end up mapping to the same vnode table entry
- For a fully associative cache, zero of the bits in an address are index bits
- The ideas of temporal and spatial locality forms part of the justification for using a write-back cache implementation
- The value of the offset into a file where the next read or write will occur is stored in the open file table and not in the descriptor table
- Every file is associated to exactly one inode
FALSE
- If two threads in the same process open the same file, they will always get the same file descriptor number
- With a file system using a hybrid index structure, the inode will contain a list of all the blocks in the file