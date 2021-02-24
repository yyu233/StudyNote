
  The fork() system call creates a new process by copying an existing
  process.  A new process is created with a copy of the page tables
  that calls fork().  These page tables are all copy on write mappings
  sharing the existing physical pages between parent and child.
