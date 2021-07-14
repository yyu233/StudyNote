Get the pids of all child processes of a given parent process <pid> by reading the /proc/<pid>/task/<tid>/children entry.

This file contain the pids of first level child processes. Recursively do this for all children pids.
