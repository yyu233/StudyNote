A init process starts serially i.e., one task starts only after the last task startup was successful and it was loaded in the memory. This often resulted into delayed and long booting time. However, systemd was not designed for speed but for getting the things done neatly which in turns avoid all the UN-necessary delay.

Features of systemd
* Clean, stateforward and efficient design.
* Simpler boot process.
* Concurrent and parallel processing at boot.
* Better API.
* Simple Unit Syntax.
* Ability to remove optional components.
* Low memory footprints.
* Improved technique to express dependencies.
* Initialization instruction written in config file and not in shell script.
* Make use of Unix Domain Socket.
* Job Scheduling using systemd Calendar Timers.
* Event Logging with journald.
* Choice of logging System events with systemd as well as syslog.
* Logs are stored in binary file.
* systemd state can be preserved to be called later in future.
* Track process using kernel’s cgroup and not PID.
* Users login managed by systemd-logind.
* Better integration with Gnome for interoperability.

|Features|	init|	systemd|
|-------|-----|-----|
|DBus Dependency – Mandatory	|No	|Yes|
|Device based Activation	|No|	Yes|
|Device dependency configuration with udev	|No|	Yes|
|Timer based Activation|	Cron/at|	Proprietary|
|Quota Management	|No|	Yes|
|Automatic Service Dependency Handling	|No|	Yes|
|Kills users Process at logout	|No	|Yes|
|Swap Management	|No	|Yes|
|SELinux integration	|No	|Yes|
|Support for Encrypted HDD|	No|	Yes|
|Static kernle module loading	|No	|Yes|
|GUI	|No|	Yes|
|List all the child processes|	No|	Yes|
|Sysv compatible	|Yes	|Yes|
|Interactive booting|	No	|Yes|
|Portable to non x86	|Yes|	No|
|Adopted on|	Several Distro|	Several Distro|
|Parallel service startup|	No	|Yes|
|Resource limit per service|	No|	Yes|
|Easy extensible startup script	|Yes|	No|
|Separate Code and Configuration File	|Yes|	No|
|Automatic dependency calculation	|No|	Yes|
|Verbose debug	|Yes|	No|
|Version	|N/A	|V44+|
|Size|	560 KB	|N/A|
|Number of Files|	75 files|	900 files + glib + DBus|
|Lines of code |LOC	15000 (Approx)	|224000 (Approx) (inc Codes, comments and white space) 125000 (Approx) (acctual code)|
