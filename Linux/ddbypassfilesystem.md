
Bypass the filesystem.

Are you able to unmount this partition that the files live on it, or mount it readonly? Do that, then something like:

dd if=/dev/PARTITION | ssh username@host "dd of=diskimage.bin"

You can then mount diskimage.bin as a loopback device on the destination side, and copy files out of it to your actual destination file system, or perhaps use the proper tools to stitch it back into an empty partition on the destination side (dangerous, but probably possible, though I've never done it.)

If you are really courageous you can dd it directly back into a partition on the destination side. I don't recommend that.
