The System Global Area (SGA) is a group of shared memory structures, known as SGA components, that contain data and control information for one Oracle Database instance. The SGA is shared by all server and background processes. Examples of data stored in the SGA include cached data blocks and shared SQL areas.


 SGA Components

|Component |	Description|
|----|----|
|Database buffer cache|Before data stored in the database can be queried or modified, it must be read from a disk and stored in the buffer cache. All user processes connected to the database share access to the buffer cache. For optimal performance, the buffer cache should be large enough to avoid frequent disk I/O operations.|
|Shared pool|The shared pool caches information that is shared among users: SQL statements that can be reused.  Information from the data dictionary such as user account data, table and index descriptions, and privileges.  Stored procedures, which are executable code that is stored in the database |
|Redo log buffer|This buffer improves performance by caching redo information until it can be written to the physical online redo log files stored on disk. Redo information and online redo log files are discussed in "About Online Redo Log Files".|
|Large pool|This optional area is used to buffer large I/O requests for various server processes.|
|Java pool|The Java pool is an area of memory that is used for all session-specific Java code and data within the Java Virtual Machine (JVM).|
|Streams pool|The Streams pool is an area of memory that is used by the Oracle Streams feature. For more information about Oracle Streams, see Oracle Streams Concepts and Administration.|
|Result cache|The result cache buffers query results. If a query is run for which the results are stored in the result cache, then the database returns the query results from the result cache instead of rerunning the query. This SGA component speeds the execution of frequently run queries.|
