Capsule Servers mirror content from the Satellite Server to establish content sources in various geographical locations. This enables host systems to pull content and configuration from the Capsule Servers in their location and not from the central Satellite Server. The recommended minimum number of Capsule Servers is therefore given by the number of geographic regions where the organization that uses Satellite operates.

Using Content Views, you can specify the exact subset of content that the Capsule Server makes available to hosts. 

The communication between managed hosts and the Satellite Server is routed through the Capsule Server that can also manage multiple services on behalf of hosts. Many of these services use dedicated network ports, but the Capsule Server ensures that a single source IP address is used for all communications from the host to the Satellite Server, which simplifies firewall administration. For more information on Capsule Servers see
