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
