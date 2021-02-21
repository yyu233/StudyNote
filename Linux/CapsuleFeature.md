There are two sets of features provided by Capsule Servers. You can configure the Capsule to mirror content from the Satellite Server. You can also use the Capsule to run services required for host management.

Content related features are:
```
Repository synchronization – the content from the Satellite Server (more precisely from selected life cycle environments) is pulled to the Capsule Server for content delivery (enabled by Pulp).
Content delivery – hosts configured to use the Capsule Server download content from that Capsule rather than from the central Satellite Server (enabled by Pulp).
Host action delivery – Capsule Server executes scheduled actions on hosts, for example package updates (provided by the Katello Agent on the host and the Qpid Dispatch Router on the Capsule).
Red Hat Subscription Management (RHSM) proxy – hosts are registered to their associated Capsule Servers rather than to the central Satellite Server or the Red Hat Customer Portal (provided by Candlepin).
Infrastructure and host management services are:

DHCP – Capsule can act as a DHCP server or it can integrate with an existing solution, including ISC DHCP servers, Active Directory, and Libvirt instances.
DNS – Capsule can act as a DNS server or it can integrate with an existing solution, including ISC DNS, Active Directory, or BIND.
TFTP – Capsule can act as a TFTP server or integrate with any UNIX-based TFTP server.
Realm – Capsule can manage Kerberos realms or domains so that hosts can join them automatically during provisioning. Capsule can integrate with an existing infrastructure including IdM, FreeIPA, and Active Directory.
Puppet Master – Capsule can act as a configuration management server by running Puppet Master.
Puppet Certificate Authority – Capsule can act as a Puppet CA to provide certificates to hosts.
Baseboard Management Controller (BMC) – Capsule can provide power management for hosts.
Provisioning template proxy – Capsule can serve provisioning templates to hosts.
OpenSCAP – Capsule can perform security compliance scans on hosts.
```
