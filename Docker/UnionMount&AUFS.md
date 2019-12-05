* Union Mount is a way of combining numerous directories into one directory that looks like it contains the content from all the them.
* AUFS stands for Another union filesystem or Advanced multi-layered unification filesystem (as of version 2). AUFS implements a union mount for Linux file systems.

Using a union filesystem allows each layer that is created to be reused by an unlimited number of images. This saves a lot of disk space and allows images to be built faster since it is just re-using an existing layer. Additionally, the read/write top layer gives the appearance that you can modify the image, but the read-only layers below actually maintain their integrity of the container by isolating the contents of the filesystem.
