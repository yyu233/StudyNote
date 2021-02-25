Two main difficulties in writing a file system.

1. large, complex API
2. file system lives in kernel space (hard to debug, easy to crash the machine)
FUSE (file system in user space) fixes #1 by providing a simpler, more uniform API. For example, in FUSE all operations take a full, absolute path (a path is absolute if it starts with "/"). There is no notion of relative paths. FUSE fixes #2 by running your file system code in user space rather than in kernel space.
