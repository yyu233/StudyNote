
A file system provides a way of separating the data on the drive into individual pieces, which are the files. It also provides a way to store data about these files — for example, their filenames, permissions, and other attributes. The file system also provides an index — a list of the files on the drive and where they’re located on the drive, so the operating system can see what’s on the drive in one place rather than combing through the entire drive to find a file.

The difference between a disk or partition and the filesystem it contains is important. A few programs (including, reasonably enough, programs that create filesystems) operate directly on the raw sectors of a disk or partition; if there is an existing file system there it will be destroyed or seriously corrupted. Most programs operate on a filesystem, and therefore won't work on a partition that doesn't contain one (or that contains one of the wrong type).

Before a partition or disk can be used as a filesystem, it needs to be initialized, and the bookkeeping data structures need to be written to the disk. This process is called making a filesystem.

