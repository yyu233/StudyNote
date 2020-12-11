
In short these are the facts to be aware of when configuring a host directory as a volume:
The file permissions set on content in the volume are identical from the perspective of host as well as container.
Only UIDs (user ids) and GIDs (group ids) matter. For example names and passwords of users and groups do not need to match or even exist in both host and container
The container OS enforces file permissions on all operations made in the container runtime according to its own configuration. For example, if a user A exists in both host and container, adding user A to group B on the host will not allow user A to write to a directory owned by group B inside the container unless group B is created inside the container as well and user A is added to it.
By default the command of a container is run as root
It is possible (on a unix-based system) to set file/directory ownership to a GID which does not belong to any actual group
