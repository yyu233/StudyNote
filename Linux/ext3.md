ext3 is a journaled file system. 

## Advantage of Journaled File System ## 

Both the size and volume of data stored on disk drives has grown exponentially over the years. The probelm with a non-journaled file system is that following a crash the fsck (filesystem consistency check) utility has to be run. fsck will scan the entire filesystem validating all entries and making sure that blocks are allocated and referenced correctly. If it finds a corrupt entry it will attempt to fix the problem. The issues here are two-fold. Firstly, the fsck utility will not always be able to repair damage and you will end up with  data in the lost+found directory. This is data that was being used by an application but the system no longer knows where they were reference from. The other problem is the issue of time. It can take a very long time to complete the fsck process on a large file system leading to unacceptable down time.

A journaled file system records information in a log area on a disk (the journal and log do not need to be on the same device) during each write. This is a essentially an "intent to commit" data to the filesystem. The amount of information logged is configurable and ranges from not logging anything, to logging what is known as the "metadata" (i.e ownership, date stamp information etc), to logging the "metadata" and the data blocks that are to be written to the file. Once the log is updated the system then writes the actual data to the appropriate areas of the filesystem and marks an entry in the log to say the data is committed.

Data Integrity   
The ext3 file system prevents loss of data integrity in the event that an unclean system shutdown occurs. The ext3 file system allows you to choose the type and level of protection that your data receives. By default, the ext3 volumes are configured to keep a high level of data consistency with regard to the state of the file system.   
Speed   
Despite writing some data more than once, ext3 has a higher throughput in most cases than ext2 because ext3's journaling optimizes hard drive head motion. You can choose from three journaling modes to optimize speed, but doing so means trade-offs in regards to data integrity if the system was to fail
