**/** Primary hierarchy root and root directory of the entire file system hierarchy     
**/bin** Essential command binaries that need to be available in a single user mode      
**/boot** boot loader files     
**/dev** device files     
**/etc** host-specific system-wide configuration files     
**/etc/opt** configuration files for add-on packages taht are stored in /opt      
**/etc/sgml** configuration files, such as catalogs, for software that processes SGML      
**/etc/X11** configuration files for the X Window System, ver 11        
**/etc/xml** configuration files, such as catalogs, for software that processes XML
**/etc/hosts**  The main purpose of this file is to resolve host names that cannot be resolved any other way. It can also be used to resolve host names on small networks with no DNS server. Regardless of the type of network the computer is on, this file should contain a line specifying the IP address of the loopback device (127.0.0.1) as localhost.localdomain.   
**/etc/resolv.conf** This file specifies the IP addresses of DNS servers and the search domain. Unless configured to do otherwise, the network intialization scripts populate this file. 
**/etc/sysconfig/network** This file specifies routing and host information for all network interfaces.    
**etc/sysconfig/network-scripts/ifcfg-\<interface-name>** For each network interface, there is a corresponding interface configuration script. Each of these files provide information specific to a particular network interface.   
**/home** users' home directories, containing saved files, personal settings, etc.      
**/lib** libraries essential for the binaries in /bin and /sbin      
**/media** mount points for removable media such as CD-ROMS  
**/mnt** temporarily mounted filesystems      
**/opt** optional application software packages   
**/proc** virtual filesystem providing process and kernel information as files. As with /dev, the files and directories are generated when your computer starts, or on the fly, as your system is running and things change. Note that even though it is called a filesystem, no part of the proc filesystem touches any disk. It exists only in the kernel's imagination. Whenever anyone tries to look at any part of the proc filesystem, the kernel makes it look as if the part existed somewhere, even though it doesn't. So, even though there is a multi-megabyte /proc/kcore file, it doesn't take any disk space.    
**/root** home directory for the root user    
**/run** run-time variable data: information about running system since last boot   
**/sbin** essential system binaries   
**/srv** site-specific data served by this system, such as data and scripts for web servers.   
**/sys** contains information about devices, drivers and sone kernel features.   
**/tmp** temporary files. Often not preserved between system reboots, and may be serverely size restricted.  
**/usr/bin** non-essential command binaries, for all users.   
**/usr/include** standard include files   
**/usr/lib** libraries for the binaries in /usr/bin   
**/usr/local** tertiary hierarchy for local data, specific to this host   
**/usr/sbin** non-essential system binaries   
**/usr/share** architecture-independent data.   
**/usr/src** source code     
**/usr/X11R6** X Window System, ver 11   
**/var** variable files - files whose content is expected to continually change during normal operation of the syste- such as logs, spool files, and temporary e-mail files.    
**/var/cache** application cache data. Such data are locally generated as a result of time-consuming I/O or calculation.   
**/var/lib**  state information. persistent data modified by programs as they run.   
**/var/lock** lock file. Files keeping track of resources currently in use.   
**/var/log** log files, various logs.   
**/var/mail** mailbox files   
**/var/opt** variable data from add-on packages that are stored in /opt   
**/var/run** run-time variable data.    
**/var/tmp** temporary files to be preserved between reboots.    



