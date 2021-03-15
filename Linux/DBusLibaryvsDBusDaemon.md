There are two major components to D-Bus: a point-to-point communication dbus library, which in theory could be used by any two processes in order to exchange messages among themselves; and a dbus daemon. The daemon runs an actual bus, a kind of "street" that messages are transported over, and to which any number of processes may be connected at any given time. Those processes connect to the daemon using the library, and it probably wouldn't make much sense to use the library for anything else. We'll be looking mostly at the situation where applications (or more generally, clients) connect to a full-blown bus.

Multiple buses may be active simultaneously on a single system. D-Bus was first built to replace the CORBA-like component model underlying the GNOME desktop environment. Similar to DCOP (which is used by KDE), D-Bus is set to become a standard component of the major free desktop environments for GNU/Linux and other platforms. A GNOME environment normally runs two kinds of buses: a single system bus for miscellaneous system-wide communication, e.g. notifications when a new piece of hardware is hooked up; and a session bus used by a single user's ongoing GNOME session. A session bus normally carries traffic under only a single user identity, but D-Bus is aware of user identities and does support flexible authentication mechanisms and access controls. The system bus may see traffic from and to any number of user identities.