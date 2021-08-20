Export of a parent folder (ro) will override a child export (rw).

```
Example exports:

/NFS_ROOT *(ro)
/NFS_ROOT/SHARE1 *(rw)
```
SHARE1 will be read-only because NFS_ROOT is read-only. 
