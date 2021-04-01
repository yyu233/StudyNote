

You could start you server with a named pipe (fifo) as its input:
```
mkfifo /tmp/srv-input
cat > /tmp/srv-input &
echo $! > /tmp/srv-input-cat-pid
cat /tmp/srv-input | myserver &
```
The cat > /tmp/srv-input & is important to avoid your server to receive a EOF. At least one process must have the fifo opened in writing so your server does not receive a EOF. The PID of this command is saved in the /tmp/srv-input-cat-pid file for latter kill.

In your case where you've already started your server, you have to use a debugger such as gdb to attach to your process to redirect its stdin to the fifo:
```
gdb -p PID
call close(0)
call open(0, "/tmp/srv-input", 0600)
```
And then do something like bellow to send input to your server (in another terminal window if necessary):
```
echo "command" > /tmp/srv-input
```
To send a EOF to your server, you need to kill the cat > /tmp/srv-input process which PID has been saved in the /tmp/srv-input-cat-pid file.

In the case of GDB, just quit GDB and EOF will be sent.
