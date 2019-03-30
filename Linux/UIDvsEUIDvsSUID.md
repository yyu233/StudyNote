## UID vs EUID vs SUID ##

Each process has three user IDs: the real user ID (real uid, or ruid), the effective user ID (effective uid, or euid), and the saved user ID (saved uid, or suid). The real uid identifies the owner of the process [i.e. the user launching the application], the effective uid is used in most access control decisions, and the saved uid stores a previous user ID so that it can be restored later.

* Real UserID : It is account of owner of this process. It defines which files that this process has access to
* Effective UserID : It is normally same as Real UserID, but sometimes it is changed to enable a non-privileged user to access files that can only be accessed by root.
*  Saved UserID : It is used when a process is running with elevated privileges (generally root) needs to do some under-privileged work, this can be achieved by temporarily switching to non-privileged account.

[Reference](https://www.osso.nl/blog/setuid-seteuid-uid-euid/)
