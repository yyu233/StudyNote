Keep Conenction
```
      TCPKeepAlive=yes
      ServerAliveInterval=15
      ServerAliveCountMax=6
      Compression=yes
      ControlMaster auto
      ControlPath /tmp/%r@%h:%p
      ControlPersist yes`

```

Client Side:

**ServerAliveInterval** The client will send a null packet to the server every 100 seconds to keep the connection alive
NULL packet Is sent by the server to the client. The same packet is sent by the client to the server. A TCP NULL packet does not contain any controlling flag like SYN, ACK, FIN etc. because the server does not require a reply from the client. The NULL packet is described here: https://tools.ietf.org/html/rfc6592

Server Side:  
**ClientAliveInterval** The server will wait 60 seconds before sending a null packet to the client to keep the connection alive   

**TCPKeepAlive** Is there to ensure that certain firewalls don't drop idle connections.   

**ClientAliveCountMax** Server will send alive messages to the client even though it has not received any message back from the client.
