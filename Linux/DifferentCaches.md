The CPU cache.

The data is put together byte by byte, and stored in the CPU cache. If the CPU cache is full and the data has not been accessed for a while, the block containing our data may get written to main memory. These are, for the most part, hidden from the application programmers.

The in-process buffers.

There is some memory set aside in the process where the data is collected so we need to make as few requests to the OS as possible, because that is comparatively expensive. The process copies the data to these buffers, which again may be backed by CPU caches, so there is no guarantee that the data is copied to main memory. The application needs to explicitly flush these buffers, for example using fclose(3) or fsync(3). The exit(3) function also does this before the process is terminated, while the _exit(2) function does not, which is why there is a big warning in the manual page for that function to call it only if you know what you are doing.

The kernel buffers

The OS then keeps its own cache, to minimize the number of requests it needs to send to the disks. This cache belongs to no process in particular, so data in there may belong to processes that have finished already, and since all accesses go through here, the next program will see the data if it has reached here. The kernel will write this data to the disks when it has time to do so or when explicitly asked.

The drive cache

The disk drives themselves also keep a cache to speed up accesses. These are written fairly quickly, and there is a command to write the remaining data in the caches and report when that is complete, which the OS uses on shutdown to make sure no data is left unwritten before powering down.
