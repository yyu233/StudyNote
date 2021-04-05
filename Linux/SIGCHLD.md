 trap signal that indicates a process started by the current process has terminated.

This allows the process to “reap” the zombie process and evaluate the exit status and make decisions on why the process terminated. This is how the shell knows to wait for a command to terminate before prompting for another command.
