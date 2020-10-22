resolv.conf is part of the standard way to resolve a host name to an IP address. It is part of the resolver library.

There are different ways to resolve your host name:

files (specifically: /etc/hosts)
dns
NIS, NIS+ or yp
The sequence in which they are used is in /etc/nsswitch.conf. This normally says

hosts:      files dns
which means that the resolver library first looks in /etc/hosts and, if it cannot find it there, will use DNS.

Now DNS will query a DNS server. Which one is determined by /etc/resolv.conf. In addition, there are a number of additional parameters that you can use to help the DNS reolution, of which search (Try this domain first for the host) is probably the most used.
