In order for systemd to function properly, the service must be started or stopped through the systemd system to maintain the correct process to unit grouping. Any operation that takes external action results in the necessary cgroup structure not being created. This happens because systemd is not aware of the special nature of the processes being started.

Some failures that can occur due to this misalignment include, but are not limited to:
* Services are not properly shutdown during system shutdown or restart events.
* Unexpected signals are delivered during user logout such as SIGHUP and SIGTERM.
* Processes that fail are not automatically restarted despite having a Restart= directive
