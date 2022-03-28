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

## Per-file metadata (on-disk)
```C
struct ext2_inode {  
    __le16 i_mode; /* File mode */  
    __le16 i_uid; /* Low 16 bits of Owner Uid */  
    __le32 i_size; /* Size in bytes */  
    __le32 i_atime; /* Access time */  
    __le32 i_ctime; /* Creation time */  
    __le32 i_mtime; /* Modification time */  
    __le32 i_dtime; /* Deletion Time */  
    __le16 i_gid; /* Low 16 bits of Group Id */  
    __le16 i_links_count; /* Links count */  
    __le32 i_blocks; /* Blocks count */  
    __le32 i_flags; /* File flags */  
    __le32 /* Machine dependent field here */  
    __le32 i_block[EXT2_N_BLOCKS];/* Pointers to blocks */  
    __le32 i_generation; /* File version (for NFS) */  
    __le32 i_file_acl; /* File ACL */  
    __le32 i_dir_acl; /* Directory ACL */  
    __le32 i_faddr; /* Fragment address */  
    /* More OS dependent stuff here. */  
};
```

## Per-file Metadata (in-memory)
```C
struct ext2_inode_info {  
    __le32 i_data[15];  
    __u32 i_flags;  
    __u32 i_faddr;  
    __u8 i_frag_no;  
    __u8 i_frag_size;  
    __u16 i_state;  
    __u32 i_file_acl;  
    __u32 i_dir_acl;  
    __u32 i_dtime;  
    __u32 i_block_group;  
    struct ext2_block_alloc_info *i_block_alloc_info;
    __u32 i_dir_start_lookup;  
    rwlock_t i_meta_lock;  
    struct mutex truncate_mutex;  
    struct inode vfs_inode;  
    struct list_head i_orphan;  
};
```

## Directory Entries
```C
struct ext2_dir_entry {  
    __le32 inode; /* Inode number */  
    __le16 rec_len; /* Directory entry length */  
    __le16 name_len; /* Name length */  
    char name[256]; /* File name */  
}
```

Minimum directory entry is 12 bytes
- Name must be at least 1 byte
- Struct needs to be 4 byte aligned

## Building a Directory

![[Pasted image 20220325144512.png]]