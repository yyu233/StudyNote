 Read-ahead speeds up file access by pre-fetching data and loading it into the page cache so that it can be available earlier in memory instead of from disk. Some workloads, such as those involving heavy streaming of sequential I/O, benefit from high read-ahead values.
The tuned tool and the use of LVM striping elevate the read-ahead value, but this is not always sufficient for some workloads. Additionally, Red Hat Enterprise Linux is not always able to set an appropriate read-ahead value based on what it can detect of your file system. For example, if a powerful storage array presents itself to Red Hat Enterprise Linux as a single powerful LUN, the operating system will not treat it as a powerful LUN array, and therefore will not by default make full use of the read-ahead advantages potentially available to the storag