hostname:D.S means screen S on display D of host hostname; the X server for this display is listening at TCP port 6000+D.

host/unix:D.S means screen S on display D of host host; the X server for this display is listening at UNIX domain socket /tmp/.X11-unix/XD (so it's only reachable from host).

:D.S is equivalent to host/unix:D.S, where host is the local hostname.

:0.0 means that we are talking about the first screen attached to your first display in your local host
