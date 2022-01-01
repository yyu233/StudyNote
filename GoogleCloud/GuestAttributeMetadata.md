Guest attributes are a specific type of custom metadata that your applications can write to while running on your virtual machine (VM) instance. Any application or user on your VM instance can both read and write data to these guest attribute metadata values.

Use guest attributes only for use cases that require small amounts of data that don't change frequently. The best use cases for guest attributes have the following characteristics:

The number of queries are limited to a maximum of 10 queries per minute per VM instance.
Queries don't exceed a burst of 3 queries per second. If this maximum rate is exceeded, Compute Engine might arbitrarily remove guest attributes that are in the process of being written. This data removal is needed to ensure that other critical system data can be written to the server.
