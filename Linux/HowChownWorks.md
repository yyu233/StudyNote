Basically, though, each file on your machine has a set of bits tacked on to it that defines its permissions and ownership. When you chown a file, you're just setting these bits.

When you chown a file to a particular user/group using the username or group name, chown will look in /etc/passwd for the username and /etc/group for the group to attempt to map the name to an ID. If the username / group name doesn't exist in those files, chown will fail.
