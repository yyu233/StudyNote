An image is a raw (literal, byte for byte) copy of a filesystem. Because this includes all the fs meta-data, you can mount it the same way you would mount a physical device with the exact same byte for byte data on it.

A tar file (aka. a 'tarchive') is an archival format that is filesystem agnostic -- although it includes information such as permissions, ownership, and maintains directory structure, it does not depend further upon the source filesystem. This means tarchives are portable from one type of filesystem to another; anywhere you have a tar utility, you should be able to use a tarfile regardless of origin.

A tarchive is not a literal byte for byte copy of a region of storage. It's a set of files structured by tar, and hence, unlike an image, its contents can be analyzed and manipulated externally (by the tar utility itself). This also means it does depend on some existing filesystem in order to be unpacked and used.

A tarchive can contain the contents of an entire filesystem, but this is not the same as containing the actual filesystem, as an image does. In order to reproduce the original fs, you would have to create an fs partition of the same type (n.b., which the tarchive contains no indication of) and unpack into it. Conversely, if you want to "unpack" an image into a subdirectory of an existing filesystem, you must mount it and copy out manually (although there may be tools to aid in this).

So, the two methodologies best suit slightly different purposes. With regard to back-ups, tar is the better choice for a number of reasons:

You are only copying actual files, and not empty space.
You are not bringing the underlying filesystem and its attendant imperfections with you (fragmentation, inconsistencies).
You can avoid including things which should never be included (e.g., /proc, /dev).
Tar files are easier to update.
