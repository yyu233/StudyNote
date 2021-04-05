File-backed mapping- In linux , there exists a file /dev/zero which is an infinite source of 0 bytes. You just open this file, and pass its descriptor to the mmap() call with appropriate flag, i.e., MAP_SHARED if you want the memory to be shared by other process or MAP_PRIVATE if you don't want sharing.  
Anonymous mapping - The similar thing that we did above can be done using anonymous mapping.For anonymous mapping, we specify the MAP_ANON flag to mmap and specify the file descriptor as -1. The resulting region is anonymous (since it's not associated with a pathname through a file descriptor) and creates a memory region that can be shared with descendant processes. The advantage is that we don't need any file for mapping the memory, the overhead of opening and closing file is also avoided.