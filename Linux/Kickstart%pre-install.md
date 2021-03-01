The commands in the %pre-install script are run after the following tasks are complete:
* System is partitioned
* File systems are created and mounted under /mnt/sysimage
* Network has been configured according to any boot options and kickstart commands
* Each of the %pre-install sections must start with %pre-install and end with %end.
* The %pre-install scripts can be used to modify the installation, and to add users and groups with guaranteed IDs before package installation.
* The %pre-install script does not run in chroot environment.
