The best way to prevent Docker container privilege escalation is not using privileged containers at all.

However, if you are running an application that requires executing with the root user, there is a way to minimize the chances of malicious activity. This is done by user namespace remapping, re-mapping the user for that specific container to a less-privileged user on the Docker host. Essentially, the container views the user as the root, while the host does not.

Re-mapping includes assigning a range of UIDs that function within the container (namespace) as normal UIDs from 0 to 65536 yet have no privileges on the host. Two files manage the user configuration – one for the user ID range (/etc/subuid) and the other for the group ID range (/etc/subgid).

By default, docker uses the dockremap user and group to make the remapping
