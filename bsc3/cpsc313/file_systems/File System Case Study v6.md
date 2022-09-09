---
course: "cpsc313"
title: "Unix v6 File System"
---

## Overview
Divided into 512-byte blocks
- Block 0: boot block
- Block 1: superblock (struct filsys)
- Blocks 2 - f(Ninodes): inodes (16 inodes/block)
- Rest of disk contains file data (and spare blocks for "bad block" handling)

![[Pasted image 20220321142459.png|700]]

## Data types
- [[Data Types v6]]

## Free space Management
- Up to 99 blocks, referenced directly in the superblock
- 1 block as the head of a linked list of blocks containing addresses of other free blocks

## Different Sized Files
- The `i_flag` indicates a small file if set to 0 and large file if set to 1
- For small files, each disk address in `i_addr` will point to a direct block
- For large files, `i_addr[0],...,i_addr[6]` will point to a indirect block and `i_addr[7]` will point to a doubly indirect block

## Directory Entries
- Entries are 16 bytes: 2 bytes for inode number and 14 bytes (right padded) of name
- A directory entry with inode = 0 is unused

```C
struct dirent {  
    uint16_t d_ino; // 2 bytes  
    char d_name[14];  
};
```