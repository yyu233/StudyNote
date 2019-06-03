## Unmount ##
Attempts to unmount a filesystem are not always successful. The most common problem is that the filesystem is busy. That is, it is currently being used by some process (i.e., instance of a program in execution). In such case an error message such as umount: /dir1: device is busy will be displayed on the screen. 

This busy state could be the result of something as simple as an GUI window being open that shows an icon of the directory containing the filesystem, in which case it can be easily solved by closing the window. Or it could be the result of a file on that filesystem being open, in which case all that is necessary is to close the file. In less obvious cases, it may be necessary to use a command such as ps or pstree to try to locate the offending process(es) and then use a command such as kill to terminate such process(es)

Another cause of failure is when a user attempts to unmount a filesystem that has already been unmounted. In such case an error message such as umount: /dir1: not mounted will be returned.
