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

## Free space Management
- Up to 99 blocks, referenced directly in the superblock
- 1 block as the head of a linked list of blocks containing addresses of other free blocks

```C
struct filsys {  
    int s_isize; /* size in blocks of the I list */  
    int s_fsize; /* size in blocks of the entire volume */  

    // IMPORTANT
    int s_nfree; /* number of in core free blocks (between 0 and 100) */  
    int s_free[100]; /* in core free blocks */  
    int s_ninode; /* number of in core I nodes (0-100) */  
    int s_inode[100]; /* in core free I nodes */  
    // IMPORTANT

    char s_flock; /* lock during free list manipulation */  
    char s_ilock; /* lock during I list manipulation */  
    char s_fmod; /* super block modified flag */  
    char s_ronly; /* super block read-only flag */  
    int s_time[2]; /* current date of last update */  
    int pad[50];  
}
```

## On-disk inode metadata
```C
struct ino {  
    int i_mode; /* File type, size, permissions */  
    char i_nlink; /* Link count */  
    char i_uid; /* Owner user id */  
    char i_gid; /* Group id */  
    char i_size0; /* most significant bits of size */  
    int i_size1; /* least sig */  

    // IMPORTANT
    int i_addr[8]; /* Disk addresses of blocks */  
    // IMPORTANT

    int i_atime[2]; /* Access time */  
    int i_mtime[2]; /* Modified time */  
}
```

## In-memory inode metadata
```C
struct inode {
    char i_flag;
    char i_count; /* reference count */
    int i_dev;  /* device where inode resides */
    int i_number; /* i number 1:1 w/device addr */
    int i_mode;
    char i_nlink; /* directory entries*/
    char i_uid;  /* owner */
    char i_gid;  /* group of owner */
    char i_size0; /* most significant of size */
    char *i_size1; /* least sig */
    int i_addr[8]; /* device addresses constituting file */
    int i_lastr; /* last logical block read */
}
```

## Different Sized Files
- The `i_flag` indicates a small file if set to 0 and large file if set to 1
- For small files, each disk address in `i_addr` will point to a direct block
- For large files, `i_addr[0],...,i_addr[6]` will point to a indirect block and `i_addr[7]` will point to a doubly indirect block

## Directory Entries
- Entries are 16 bytes: 2 bytes for inode number and 14 bytes (right padded) of name
- A directory entry with inode = 0 is unused

```C
struct dirent {  
int d_ino; // 16 bits  
char d_name[14];  
};
```