Almost everything in Linux can be considered a file, but the main difference between a regular file and a named pipe is that a named pipe is a special instance of a file that has no contents on the filesystem.

Here is quote from man fifo:

A FIFO special file (a named pipe) is similar to a pipe, except that it is accessed as part of the filesystem. It can be opened by multiple processes for reading or writing. When processes are exchanging data via the FIFO, the kernel passes all data internally without writing it to the filesystem. Thus, the FIFO special file has no contents on the filesystem; the filesystem entry merely serves as a reference point so that processes can access the pipe using a name in the filesystem.

The kernel maintains exactly one pipe object for each FIFO special file that is opened by at least one process. The FIFO must be opened on both ends (reading and writing) before data can be passed. Normally, opening the FIFO blocks until the other end is opened also.

So actually a named pipe does nothing until some process reads and writes to it. It does not take any space on the hard disk (except a little bit of meta information), it does not use the CPU
