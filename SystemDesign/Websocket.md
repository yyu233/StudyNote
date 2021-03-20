WebSocket solves a few issues with HTTP:
* Bi-directional protocol — either client/server can send a message to the other party (In HTTP, the request is always initiated by the client and the response is processed by the server — making HTTP a uni-directional protocol)
* Full-duplex communication — client and server can talk to each other independently at the same time.
* Single TCP connection — After upgrading the HTTP connection in the beginning, client and server communicate over that same TCP connection throughout the lifecycle of WebSocket connection.
