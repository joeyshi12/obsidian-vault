```C
// On-disk metadata
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

// In-memory metadata
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

// Modern versions of this has TYPE
struct ext2_dir_entry {  
    __le32 inode; /* Inode number */  
    __le16 rec_len; /* Directory entry length */  
    __le16 name_len; /* Name length */  
    char name[256]; /* File name */  
};
```