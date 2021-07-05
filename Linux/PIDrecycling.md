Under Unix, process IDs are usually allocated on a sequential basis, beginning at 0 and rising to a maximum value which varies from system to system. Once this limit is reached, allocation restarts at zero and again increases. However, for this and subsequent passes any PIDs still assigned to processes are skipped.

so it's really a very simple policy for "generation", just increment a counter, and "recycling", just wrap the number around at a max value and keep incrementing until you find a number that was assigned to a process that has finished and has been removed from the process table.

