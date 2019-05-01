There is a low level difference between cp and install, at least on Linux. If copying over an existing file, cp overwrites the existing inode of the file, while install always creates a new inode for the same file name.

This makes a difference when installing a new version of a running binary. Using cp causes an EBUSY error, while install will succeed. The running binary will still use the old version, but the new version is used if the program is restarted.
