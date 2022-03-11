---
course: "cpsc313"
title: "File Systems"
---

## File: stream of bytes
Reading from the file increments the current offset
- After reading 4 bytes the offset moves  by 4
- Read and write **SHARE** the same offset
- Offset indicates the next location from which to read or to which to write
- Kernel keeps track of file descriptions in array (file descriptor table)

Each open file needs an offset for reading and writing.
The file descriptor must help us find
- The file's data (PERSISTENT)
- The file's **metadata** (how large the file is, who can access the file) (PERSISTENT)
- The file offset; no file is open when system is first booted => (NOT PERSISTENT)

## Stream of bytes => blocks
A file is a stream of bytes, but

data can only be read from a disk one block/sector at a time

Reading a byte requires that we retrieve a block from the disk
- How do we find the block?

**Which block?**
`Offset / sizeof(block) = blockNumber`, but
- This is not a disk address!
- This block number is relative to the start of this file
- There are lots of files on the disk and lots of blocks/sectors as well


## File name hierarchy
- A file name of the form /A/BC/DE/file

![[Pasted image 20220309143107.png|500]]

```
// open(pathname)

Offset => Logical Block Number (LBN) => Metadata => Disk address
                                           ^
                                           |
                                        pathname
```
