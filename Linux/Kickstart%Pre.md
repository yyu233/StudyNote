The %pre scripts are run on the system immediately after the Kickstart file has been loaded, but before it is completely parsed and installation begins
* All the Kickstart %pre install script must start with %pre and end with %end line
* Commands related to networking, storage, and file systems are available to use in the %pre script, in addition to most of the utilities in the installation environment /sbin and /bin directories.
* The %pre script does not run in the chroot environment.
