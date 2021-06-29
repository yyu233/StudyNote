The size of a file and the space it occupies on your hard drive are rarely the same. Disk space is allocated in blocks. If a file is smaller than a block, an entire block is still allocated to it because the file system doesn’t have a smaller unit of real estate to use.

Unless a file’s size is an exact multiple of blocks, the space it uses on the hard drive must always be rounded up to the next whole block. For example, if a file is larger than two blocks but smaller than three, it still takes three blocks of space to store it.

Two measurements are used in relation to file size. The first is the actual size of the file, which is the number of bytes of content that make up the file. The second is the effective size of the file on the hard disk. This is the number of file system blocks necessary to store that file.

