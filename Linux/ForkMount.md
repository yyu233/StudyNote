       -F, --fork
              (Used in conjunction with -a.)  Fork off a new incarnation of mount for each
              device.   This  will  do  the  mounts  on different devices or different NFS
              servers in parallel.  This has the advantage that it  is  faster;  also  NFS
              timeouts go in parallel. A disadvantage is that the mounts are done in unde-
              fined order.  Thus, you cannot use this option if you  want  to  mount  both
              /usr and /usr/spool.
