## Run Level ## 

Linux kernel has booted -> init program reads the /etc/inittab file -> if no specified value, the system will enter the default runlevel.    
Init spawns all other processes, runs as a daemon and typically has PID 1.   
The applications that are started by init are located in the /etc/rc.d folder.      

On RedHat, run ```chkconfig --list``` to display a list of services whether they are enabled or disabled for each runlevel.

|Run Level | Mode |Action|
|----|---|---|
|0|Halt|Shuts down system|
|1|Single-user mode|Does not configure network interfaces, start daemons, or allow non-root logins|
|2|Multi-User Mode|	Does not configure network interfaces or start daemons|
|3|Multi-User Mode with Networking|Starts the system normally|
|4|Undefined|Not used/User-definable|
|5|X11|As runlevel 3 + display manager(X)|
|6|Reboot|Reboots the system|




