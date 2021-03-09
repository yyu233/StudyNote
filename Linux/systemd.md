systemd is a system and service manager for Linux operating systems. When run as first process on boot (as PID 1), it acts as init system that brings up and maintains userspace services.

When run as a system instance, systemd interprets the configuration file system.conf and the files in system.conf.d directories; when run as a user instance, systemd interprets the configuration file user.conf and the files in user.conf.d directories. 

* Socket-based activation — At boot time, systemd creates listening sockets for all system services that support this type of activation, and passes the sockets to these services as soon as they are started. This not only allows systemd to start services in parallel, but also makes it possible to restart a service without losing any message sent to it while it is unavailable: the corresponding socket remains accessible and all messages are queued.

Systemd uses socket units for socket-based activation.

* Bus-based activation — System services that use D-Bus for inter-process communication can be started on-demand the first time a client application attempts to communicate with them. Systemd uses D-Bus service files for bus-based activation.
* Device-based activation — System services that support device-based activation can be started on-demand when a particular type of hardware is plugged in or becomes available. Systemd uses device units for device-based activation.
* Path-based activation — System services that support path-based activation can be started on-demand when a particular file or directory changes its state. Systemd uses path units for path-based activation.
* Mount and automount point management — Systemd monitors and manages mount and automount points. Systemd uses mount units for mount points and automount units for automount points.
* Aggressive parallelization — Because of the use of socket-based activation, systemd can start system services in parallel as soon as all listening sockets are in place. In combination with system services that support on-demand activation, parallel activation significantly reduces the time required to boot the system.
Transactional unit activation logic — Before activating or deactivating a unit, systemd calculates its dependencies, creates a temporary transaction, and verifies that this transaction is consistent. If a transaction is inconsistent, systemd automatically attempts to correct it and remove non-essential jobs from it before reporting an error.
* Backwards compatibility with SysV init — Systemd supports SysV init scripts as described in the Linux Standard Base Core Specification, which eases the upgrade path to systemd service units.
