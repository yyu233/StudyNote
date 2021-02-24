Multiple Page Table Entries can map the same physical page.  Access through
  these virtual addresses (often in different processes) all show the same
  contents, and changes to it are immediately visible to all users.  (Shared
  writable mappings are a common high-performance inter-process communication
  mechanism.)
