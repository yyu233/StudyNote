How should you go about choosing a file system that meets your application requirements? The first step is to understand the target system on which you are going to deploy the file system. The following questions can be used to inform your decision:

Do you have a large server?
Do you have large storage requirements or have a local, slow S-ATA drive?
What kind of I/O workload do you expect your application to present?
What are your throughput and latency requirements?
How stable is your server and storage hardware?
What is the typical size of your files and data set?
If the system fails, how much downtime can you suffer?
Do you foresee the need to shrink (reduce) the filesystem size?
Depending on the answers to the above questions, your choice might be obvious. If both your server and your storage device are large, and there is no need to shrink (reduce) the filesystem size, XFS is likely to be the best choice. Even with smaller storage arrays, XFS performs very well when the average file sizes are large (for example, hundreds of megabytes in size).

If your existing workload has performed well with Ext3, staying with Ext3 on Red Hat Enterprise Linux 5 or migrating to Ext4 on Red Hat Enterprise Linux 6 or Red Hat Enterprise Linux 7 should provide you and your applications with a very familiar environment. Two key advantages of Ext4 over Ext3 on the same storage include faster file system check and repair times and higher streaming read and write performance on high-speed devices.

Another way to characterize this is that the Ext4 file system variants tend to perform better on systems that have limited I/O capability. Ext3 and Ext4 perform better on limited bandwidth (< 200MB/s) and up to ~1,000 IOPS capability. For anything with higher capability, XFS tends to be faster. XFS also consumes about twice the CPU-per-metadata operation compared to Ext3 and Ext4, so if you have a CPU-bound workload with little concurrency, then the Ext3 or Ext4 variants will be faster. In general, Ext3 or Ext4 is better if an application uses a single read/write thread and small files, while XFS shines when an application uses multiple read/write threads and bigger files.

We recommend that you measure the performance of your specific application on your target server and storage system to make sure you choose the appropriate type of file system.

Red Hat Enterprise Linux 6 has new file system capabilities and performance characteristics. Key features that have been introduced in Red Hat Enterprise Linux 6 include support for the SSD “trim” command, support for thinly provisioned storage, and automated detection and alignment of new file systems on many types of storage devices.
