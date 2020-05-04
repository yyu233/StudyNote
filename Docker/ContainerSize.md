To view the approximate size of a running container, you can use the docker ps -s command. Two different columns relate to size.

size: the amount of data (on disk) that is used for the writable layer of each container.

virtual size: the amount of data used for the read-only image data used by the container plus the container’s writable layer size. Multiple containers may share some or all read-only image data. Two containers started from the same image share 100% of the read-only data, while two containers with different images which have layers in common share those common layers. Therefore, you can’t just total the virtual sizes. This over-estimates the total disk usage by a potentially non-trivial amount.

The total disk space used by all of the running containers on disk is some combination of each container’s size and the virtual size values. If multiple containers started from the same exact image, the total size on disk for these containers would be SUM (size of containers) plus one image size (virtual size- size).

This also does not count the following additional ways a container can take up disk space:

Disk space used for log files if you use the json-file logging driver. This can be non-trivial if your container generates a large amount of logging data and log rotation is not configured.
Volumes and bind mounts used by the container.
Disk space used for the container’s configuration files, which are typically small.
Memory written to disk (if swapping is enabled).
Checkpoints, if you’re using the experimental checkpoint/restore feature.
