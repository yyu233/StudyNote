Ramfs is a very simple FileSystem that exports Linux's disk cacheing mechanisms (the page cache and dentry cache) as a dynamically resizable ram-based filesystem.

Normally all files are cached in memory by Linux. Pages of data read from backing store (usually the ?block_device the filesystem is mounted on) are kept around in case it's needed again, but marked as clean (freeable) in case the Virtual Memory system needs the memory for something else. Similarly, data written to files is marked clean as soon as it has been written to backing store, but kept around for cacheing purposes until the VM reallocates the memory. A similar mechanism (the dentry cache) greatly speeds up access to directories.

With ramfs, there is no backing store. Files written into ramfs allocate dentries and page cache as usual, but there's nowhere to write them to. This means the pages are never marked clean, so they can't be freed by the VM when it's looking to recycle memory            
[Reference](https://wiki.debian.org/ramfs)
