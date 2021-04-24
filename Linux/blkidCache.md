  When device is specified, tokens from only this device are displayed.  It is  possible  to
       specify  multiple  device  arguments  on  the command line.  If none is given, all devices
       which appear in /proc/partitions are shown, if they are recognized.

       Note that blkid reads information directly from devices and for non-root users it  returns
       cached  unverified  information.   It  is  better to use lsblk --fs to get a user-friendly
       overview of filesystems and devices.  lsblk(8) is also easy to use in scripts.   blkid  is
       mostly designed for system services and to test libblkid functionality.
