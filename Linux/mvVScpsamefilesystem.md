That’s the way the mv tool is programmed to move a file: Leave the inode unchanged (unless the file is being moved to a different filesystem), and preserve its ownership and permissions.

The cp command, unlike mv, creates a brand new data object in your filesystem. It has a new inode location, and it is subject to your active umask. 
