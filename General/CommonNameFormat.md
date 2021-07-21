The common name is not a URL. It doesn’t include any protocol (e.g. http:// or https://), port number, or pathname. For instance, https://example.com or example.com/path are incorrect. In both cases, the common name should be example.com.

It must precisely match the server name where the certificate is installed. If the certificate is issued for a subdomain, it should be the full subdomain. For instance, for the www and api subdomains of example.com, the common name will be www.example.com or api.example.com, and not example.com.
