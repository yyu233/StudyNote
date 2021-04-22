The initrd.img on the install media is what we call the stage1 image. It contains a program called loader, whose only job is to find and load images/install.img.

install.img is the stage2 image. This is where Anaconda actually lives - it's a squashfs image that contains the installer's root filesystem
