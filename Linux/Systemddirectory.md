|Directory	|Description|
|-----|----|
|/usr/lib/systemd/system/|Systemd unit files distributed with installed RPM packages.|
|/run/systemd/system/|Systemd unit files created at run time. This directory takes precedence over the directory with installed service unit files.|
|/etc/systemd/system/|Systemd unit files created by systemctl enable as well as unit files added for extending a service. This directory takes precedence over the directory with runtime unit files.|
