## Hard Link ##

Hard Link acts as a shortcut to a file. Hard Link can be created to other hard link. They cannot be created for directories. They cannot cross filesystem boundaries or span partitions.

## Soft Link ##

Soft Link does not contain the data in target file. It can link to directories or files on remote computer network. 

## In General ##
A file in the file system is basically a link to an inode. A hard link then just creates another file with a link to the same underlying inode.When you delete a file it removes one link to the underlying inode. The inode is only deleted (or deletable/over-writable) when all links to the inode have been deleted.
A symbolic link is a link to another name in the file system.
Once a hard link has been made the link is to the inode. deleting renaming or moving the original file will not affect the hard link as it links to the underlying inode. Any changes to the data on the inode is reflected in all files that refer to that inode.

[Reference](https://blog.usejournal.com/what-is-the-difference-between-a-hard-link-and-a-symbolic-link-8c0493041b62)    
