In computer networks, a reverse proxy is a type of proxy server that retrieves resources on behalf of a client from one or more servers. These resources are then returned to the client, appearing as if they originated from the proxy server itself.[1] Unlike a forward proxy, which is an intermediary for its associated clients to contact any server, a reverse proxy is an intermediary for its associated servers to be contacted by any client. In other words, a proxy acts on behalf of the client(s), while a reverse proxy acts on behalf of the server(s).

A reverse proxy can reduce load on its origin servers by caching static content and dynamic content, known as web acceleration. Proxy caches of this sort can often satisfy a considerable number of website requests, greatly reducing the load on the origin server(s).


Additional benefits include:

Increased security - Hide information about backend servers, blacklist IPs, limit number of connections per client
Increased scalability and flexibility - Clients only see the reverse proxy's IP, allowing you to scale servers or change their configuration
SSL termination - Decrypt incoming requests and encrypt server responses so backend servers do not have to perform these potentially expensive operations
Removes the need to install X.509 certificates on each server
Compression - Compress server responses
Caching - Return the response for cached requests
Static content - Serve static content directly
HTML/CSS/JS
Photos
Videos
Etc

