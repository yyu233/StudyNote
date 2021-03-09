## Service units:
A unit configuration file whose name ends in .service encodes
information about a process controlled and supervised by systemd.
— systemd.service(5)

Systemd service units are the units that actually execute and keep track of programs and daemons, and dependencies are used to make sure that services are started in the right order. They are the most commonly used type of units.

## Socket units:
A unit configuration file whose name ends in ".socket" encodes
information about an IPC or network socket or a file system FIFO
controlled and supervised by systemd, for socket-based activation.
— systemd.socket(5)

Socket units on the other hand don't actually start daemons on their own. Instead, they just sit there and listen on an IP address and a port, or a UNIX domain socket, and when something connects to it, the daemon that the socket is for is started and the connection is handed to it.

This is useful for making sure that big daemons that take up a lot of resources but are rarely used aren't running and taking up resources all the time, but instead they are only started when needed.

## Target units:
A unit configuration file whose name ends in ".target" encodes
information about a target unit of systemd, which is used for grouping
units and as well-known synchronization points during start-up.
— systemd.target(5)

Targets are used for grouping and ordering units. They are somewhat of a rough equivalent to runlevels in that at different targets, different services, sockets, and other units are started. Unlike runlevels, they are much more free-form and you can easily make your own targets for ordering units, and targets have dependencies among themselves.

For instance, multi-user.target is what most daemons are grouped under, and it requires basic.target to be activated, which means that all services grouped under basic.target will be started before the ones in multi-user.target.
