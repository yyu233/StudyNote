blk-availability service is used as a helper program which correctly unmounts/disables LVM when shutting the system down.

It does nothing when starting a service but run blkdeactivate command which makes all the VGs unmounted or disabled when stopping a service.

Unless there is specific requirement, services should be automatically started up in runlevel 1~5. As for runlevel 0 and 6 which mean stopping system, it is desirable to set service stop.
