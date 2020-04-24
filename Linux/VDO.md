So if we put the VDO layer between a file system and a block device, how will it influence the I/O performance for the filesystem?

The following data was collected using spinning disks as backend, on a system with 32 GB RAM and 12 cores at 2.4Ghz.

Column ‘deploy to file system’ shows the time it took to copy a directory with ~5GB of data from RAM (/dev/shm) to the filesystem. Column ‘copy on file system’ shows the time required to make a single copy of the 5GB directory which was deployed in the first step. The time was averaged over multiple runs, always after removing the data and emptying the file system caches. Publicly available texts from the Project Gutenberg were used as data, quite nicely compressible.

filesystem backend

deploy to file system

copy on file system

XFS ontop of normal LVM volume

28sec

35sec

XFS on VDO device, async mode

55sec

58sec

XFS on VDO device, sync mode

71sec

92sec

 
Deployment to VDO backend is slower than to plain LVM backend.

I was initially wondering whether copies on top of a VDO backed volume would be faster than copies on top of a LVM volume - they are not. When data on a VDO backed file system is copied, for example with ‘cp’, then the copy is by definition a duplicate. After VDO identifies this as candidate for duplicate data, it does a read comparison to be sure.

When using SSD or NVDIMM as backend, extra tuning should be done. VDO is designed to properly deal with many parallel I/O requests in mind. In my tests here I did not optimize for parallelization, I just used single instances of ‘rsync’, ‘tar’ or ‘cp’. Also for these, VDO can break up requests from applications to write big files into many small requests - if the underlying media is, for example, a high-speed NVMe SSD, then this can help performance.

Something good to know for testing: I noticed GNU tar reading data incredibly fast when writing to /dev/null. Turns out that ‘tar’ is detecting this situation and not reading at all. So ‘tar cf /dev/null /usr’ is not doing what you probably expect, but ‘tar cf - /usr|cat >/dev/null’ is.
