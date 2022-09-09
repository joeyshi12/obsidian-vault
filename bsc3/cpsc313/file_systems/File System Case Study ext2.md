---
course: "cspc313"
title: "File System Case Study ext2"
---

Keeps multiple copies of superblock and block descriptor table so that we can still read the rest of the file system
How many? We need a copy on every platter perhaps each surface spread across disk for insurance

## Disk Layout: Block Groups
Superblock and block descriptor describes the whole file system
Benefit of storing huge files and storing related blocks together

![[Pasted image 20220325141407.png]]

## Free Space Management: Bitmaps
A bitmap is a collection of bits where each bit corresponds to one object and the value of the bit indicates if the object is in use or available/free.
Bit = 1 means the block is in use; Bit = 0 means the block is available

If we have 512B blocks, then we can hold 512B * 8bits/B = 4096 bits
This means we can have 4096 inodes or data blocks


## How large are block groups?
If we have 512B block size and 1 block of bitmap for inodes, then we have up to 4096 inodes in a block group
Suppose inodes are 64B. Then, we have $\frac{512 bytes/block}{64 bytes/inodes} = 8 inodes/block$

Each block is 512B, so we can store $512 \cdot 4096 = 2MB$ of data in a block group


## Example
Suppose blocks are 8192 bytes; inodes are 128 bytes
Q1: How many bits fit in a block?
8192 * 8 = 2^16 = 64K bits

Q2: How much data can we have in a block group?
2^13 * 2^16 = 2^29 = 512MB

Q3: What is the maximum number of inodes we can have?
64K

Q4: How many blocks will it take to hold all our inodes?
$\frac{64 KB/inode}{64 B/inode} = 1024$ blocks


## Data Types
- [[Data Types ext2]]


## Directory Entries
Minimum directory entry is 12 bytes
- Contains type info
- Name must be at least 1 byte
- Struct needs to be 4 byte aligned


## Building a Directory

![[Pasted image 20220325144512.png]]