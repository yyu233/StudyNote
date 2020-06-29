```
rpmdb: Lock table is out of available locker entries
error: db4 error(22) from db->close: Invalid argument
error: cannot open Packages index using db3 - Cannot allocate memory (12)
error: cannot open Packages database in /var/lib/rpm
Make a backup of /var/lib/rpm in case you break something:

tar cvzf rpmdb-backup.tar.gz /var/lib/rpm
Remove the Berkeley databases that rpm uses:

rm /var/lib/rpm/__db.00*
Make rpm rebuild the databases from scratch (may take a short while):

rpm --rebuilddb
Now, check rpm to make sure everything is okay:

rpm -qa | sort
Why does this happen?

When rpm accesses the Berkeley database files, it makes temporary locker entries within the tables while it searches for data. If you control-c your rpm processes often, this issue will occur much sooner because the locks are never cleared.

```
