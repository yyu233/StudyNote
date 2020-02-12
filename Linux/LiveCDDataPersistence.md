The read-only part of the liveimage is mapped to /dev/mapper/live-osimg-min and the writable part of the filesystem is mapped to /dev/mapper/live-rw.
Usually the rw stuff is lost when you shutdown the livecd, but with a persistent overlay the changes are written there and reloaded on next boot.
