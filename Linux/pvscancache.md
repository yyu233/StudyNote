       Scanning  disks is required to read LVM metadata and identify LVM PVs.  Once read, lvmetad
       caches the metadata so that LVM commands can read it without  repeatedly  scanning  disks.
       This  is  helpful  because  scanning  disks  is  time consuming, and frequent scanning may
       interfere with the normal work of the system and disks.

       When lvmetad is not used, LVM commands revert to scanning disks to read metadata.  Any LVM
       command  that  needs  metadata  will  scan disks for it; running the pvscan command is not
       necessary for the sake of other LVM commands.

       When lvmetad is used, LVM commands avoid scanning disks by reading metadata from  lvmetad.
       When  new  disks  appear, they must be scanned so their metadata can be cached in lvmetad.
       This is done by the command pvscan --cache, which scans disks and passes the  metadata  to
       lvmetad.
