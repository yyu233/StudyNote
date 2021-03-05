
Using Network Information Service (NIS)
Network Information Service (NIS) was developed by Sun Microsystems as a way to share information among all computers in a local area network. The types of information NIS most commonly uses include the following:

User names and passwords from files such as /etc/passwd and /etc/shadow

Group information from the /etc/group file

Normally, each system has its own copy of information in respective files, and any changes require updating the files on each system individually. Using NIS, you can maintain a single set of configuration files for a collection of computers in an NIS server. All other computers running NIS clients can then access the files. For example, if your user name and password are in the NIS password database, you will be able to log in on all computers on the network running NIS client programs.


NIS was originally called Sun Yellow Pages (YP), but the name Yellow Pages is a registered trademark of British Telecom in the United Kingdom, so Sun Microsystems had to change the name. However, many NIS commands, and the NIS package names, begin with the letters yp.

If you want to use NIS in a network, you must set up at least one NIS server. You can have multiple NIS servers in a network, each serving a different collection of computers. You can also have a master NIS server and one or more slave NIS servers that receive a copy of the master's database. The group of computers a master NIS server supports is called an NIS domain or YP domain.

The master NIS server runs the ypserv daemon (this is the NIS server daemon) that maintains the shared information in DBM databases. (DBM refers to Data Base Management, a library of functions that maintain key-value pairs in a database.) The NIS databases are called maps. You can create these NIS maps directly from the text configuration files-such as /etc/passwd and /etc/group-by using the /usr/ lib/yp/makedbm program that comes with the NIS server software. More accurately, the ypserv daemon uses the Makefile in the /var/yp directory to create the maps for all shared configuration files.

The master NIS server provides the maps to all NIS client computers. The clients run the ypbind daemon through which various client programs access the master NIS server. In addition to a master server, one or more NIS slave servers may be set up to provide the NIS maps in case the master is unavailable or down. The NIS slave servers periodically copy the NIS maps from the master server (using the /usr/ lib/yp/ypxfr command) and are able to provide these maps to clients when the master is down.

You can think of NIS as a way of distributing the same set of configuration files among all computers in an NIS domain. You get the benefits of sharing the same files (such as the same user name and password for all machines), yet you can still edit and maintain just one set of files-the files on the master NIS server.
