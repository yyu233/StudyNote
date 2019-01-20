## RAID ##

RAID put data across multiple disks. This allows I/O operation simultaneously. Storing data reduntantly increases fault tolerance.

## RAID Controller ##

RAID Controller is a logical unit to manage the physical disks in RAID. It is a level of abstraction between OS and disks. 

## RAID 0 ##

RAID 0 has block-level striping but no redundancy. It is best for non-critical data storage and fast read and write.

## RAID 1 ##

RAID 1 has no striping but redundancy. Disk mirroring.It is best for application requiring high availablity such as email and online transaction.

## RAID 2 ##

RAID 2 has bit-level striping but no redundancy. (Why bit-level?) It uses some disks for parity. Parity is used for error correction. (Not currently in use)

## RAID 3 ##

RAID 3 has byte-level striping and one disk for parity. (Rarely in use)

## RAID 4 ##

RAID 4 has block-level striping and one disk for parity. Random read is good because read can be done simultaneously across disks. Random write is bad because each write needs change of parity in one disk. The next write needs to wait till the last write is done.

## RAID 5 ##

RAID 5 has block-level striping and parity is distributed among disks. 

## RAID 10 ##

RAID 1 + RAID 0
