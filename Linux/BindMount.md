 Note that no filesystem type is specified either way: making a bind mount doesn't involve a filesystem driver, it copies the kernel data structures from the original mount.

mount --bind also support mounting a non-directory onto a non-directory: /some/where can be a regular file (in which case /else/where needs to be a regular file too).

A Linux bind mount is mostly indistinguishable from the original. The command df -T /else/where shows the same device and the same filesystem type as df -T /some/where. The files /some/where/foo and /else/where/foo are indistinguishable, as if they were hard links. It is possible to unmount /some/where, in which case /else/where remains mounted.
