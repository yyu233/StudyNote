First off, a "port" is just a number. All a "connection to a port" really represents is a packet which has that number specified in its "destination port" header field.

Now, there are two answers to your question, one for stateful protocols and one for stateless protocols.

For a stateless protocol (ie UDP), there is no problem because "connections" don't exist - multiple people can send packets to the same port, and their packets will arrive in whatever sequence. Nobody is ever in the "connected" state.

For a stateful protocol (like TCP), a connection is identified by a 4-tuple consisting of source and destination ports and source and destination IP addresses. So, if two different machines connect to the same port on a third machine, there are two distinct connections because the source IPs differ. If the same machine (or two behind NAT or otherwise sharing the same IP address) connects twice to a single remote end, the connections are differentiated by source port (which is generally a random high-numbered port).

Simply, if I connect to the same web server twice from my client, the two connections will have different source ports from my perspective and destination ports from the web server's. So there is no ambiguity, even though both connections have the same source and destination IP addresses.

Ports are a way to multiplex IP addresses so that different applications can listen on the same IP address/protocol pair. Unless an application defines its own higher-level protocol, there is no way to multiplex a port. If two connections using the same protocol simultaneously have identical source and destination IPs and identical source and destination ports, they must be the same connection.


