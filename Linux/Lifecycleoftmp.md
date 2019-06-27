## Life Cycle of tmp folder ##

* On Debian-like systems: on boot (the rules are defined in /etc/default/rcS).
* On RedHat-like systems: by age (RHEL6 it was /etc/cron.daily/tmpwatch ; RHEL7 and RedHat-like with systemd it's configured in /usr/lib/tmpfiles.d/tmp.conf, called by systemd-tmpfiles-clean.service).
* On Gentoo /etc/conf.d/bootmisc.
