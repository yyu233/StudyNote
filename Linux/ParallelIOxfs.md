XFS is a highly scalable, high-performance 64-bit journaling file system developed at SGI in 1993 and ported to Linux in 2002. It supports highly parallel I/O and filesystem sizes up to 9 Exabytes, and journals only the file system metadata, not the user data.  Some key performance enhancing features of XFS are:

Parallelized access via allocation groups ensures multiple threads can perform I/O simultaneously on the same volume.
Extent based allocation reduces fragmentation, metadata size, and improves I/O performance by allowing fewer and larger I/O operations.
Delayed allocation improves data contiguity and performance. Fragmentation is reduced by combining writes and allocating extents in large chunks, and files written randomly (such as those that are memory mapped) can be allocated contiguously
