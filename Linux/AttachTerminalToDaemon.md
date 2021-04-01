First, create a pipe: mkfifo /tmp/fifo. Use gdb to attach to the process: gdb -p PID

Then close stdin: call close (0); and open it again: call open ("/tmp/fifo", 0600)

Finally, write away (from a different terminal, as gdb will probably hang):

echo blah > /tmp/fifo
