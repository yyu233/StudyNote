* As mentioned it supports metadata journaling, which facilitates quicker crash recovery.
* Tightly integrated backup and restore utilities
* Online defragmentation and growth: This filesystem can be defragmented and enlarged while mounted and active.
* Comprehensive diagnostics capabilities
* Scalable and fast repair utilities. XFS scales to exabytes more than 500TB
* Optimizations for streaming video workloads
* B-tree indexing for scalability of free space management
* Ability to support a large number of concurrent operations
* Extensive run-time metadata consistency checking
* Sophisticated metadata read-ahead algorithms
* Delayed, Extent-based allocation
* Dynamically allocated inodes
* Extended attributes (xattr): This allows the system to associate several additional name/value pairs per file. It is enabled by default.
* Compared to Ext4, XFS has a relatively poor performance for single threaded, metadata-intensive workloads. This includes workload that creates or deletes large numbers of small files in a single thread.
* Quota journaling: This avoids the need for lengthy quota consistency checks after a crash
