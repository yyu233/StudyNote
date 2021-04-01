  The exec() system call executes a new file in the current process
  context.  It blanks the process's current page table, discarding all
  existing mappings, and replaces them with a fresh page table containing
  a small number of new mappings, including an executable mmap() of the new
  file passed to the exec() call, a small amount of administrative space
  containing the environment variables and command line arguments passed
  into the new program, a new process stack, and so on.

  The normal way to launch a new process in Unix-like systems is to call
  fork(), followed immediately by a call to exec() in the new process.
  Thus fork() copies the parent process's existing process's memory mappings
  into the new process, then exec() immediately discards them again.
  Because these were shared mappings, the fork() allocates a lot of virtual
  space but consumes very few new physical pages

The exec command replaces the current shell process with the specified command. Normally, when you run a command a new process is spawned (forked). The exec command does not spawn a new process. Instead, the current process is overlaid with the new command. In other words the exec command is executed in place of the current shell without creating a new process. 
