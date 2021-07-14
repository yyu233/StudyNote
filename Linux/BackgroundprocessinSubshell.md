The $(...) command substitution mechanism waits for EOF on the pipe that the subshell's stdout is connected to. So even if you background a command in the subshell, the main shell will still wait for it to finish and close its stdout. To avoid waiting for this, you need to redirect its output away from the pipe.

echo "$( cat file1; sleep 3 >/dev/null 
