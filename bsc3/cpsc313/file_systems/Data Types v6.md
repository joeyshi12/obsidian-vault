
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
};

// On-disk inode
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
};

// In-memory inode
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
};

struct dirent {  
    uint16_t d_ino; // 2 bytes  
    char d_name[14];  
};
```