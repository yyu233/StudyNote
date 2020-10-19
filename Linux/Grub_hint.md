This is not described in the GRUB Manual but there is documentation to be found in GRUB itself (search --help on the GRUB shell):
```
--hint
    First try the device HINT.
    If HINT ends in comma, also try subpartitions

--hint-ieee1275
    First try the device HINT if currently running on IEEE1275.
    If HINT ends in comma, also try subpartitions

--hint-bios
    First try the device HINT if currently running on BIOS.
    If HINT ends in comma, also try subpartitions

--hint-baremetal
    First try the device HINT if direct hardware access is supported.
    If HINT ends in comma, also try subpartitions

--hint-efi
    First try the device HINT if currently running on EFI.
    If HINT ends in comma, also try subpartitions

--hint-arc
    First try the device HINT if currently running on ARC.
    If HINT ends in comma, also try subpartitions
Now what is the point of "First try device"?

You have to understand that search is a potentially slow operation.

Maybe you have 50 drives, each with 100 partitions, and now search has to go through all of these ... until it finally finds the UUID you were looking for in the 2356th attempt.

Or maybe you have a very slow device and checking for its UUID causes search to be stuck for a while. There's --no-floppy to avoid the most common case, I guess - but other devices can also be slow.

With --hint, you set a device to check first. Provided the hint was correct, you skip the otherwise potentially lengthy search operation altogether. So this is a speed optimization. (Probably won't be noticable with just one drive, three partitions)\
```
