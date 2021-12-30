A health check sends probe requests to an instance using a specified protocol, such as HTTP(S), SSL, or TCP. For more information, see how health checks work and health check categories, protocols, and ports.

The health check in this tutorial is an HTTP health check that probes the HTTP path /health on port 80. For an HTTP health check, the probe request passes only if the path returns an HTTP 200 (OK) response. For this tutorial, the demo web server defines the path /health to return an HTTP 200 (OK) response when healthy or an HTTP 500 (Internal Server Error) response when unhealthy. 
