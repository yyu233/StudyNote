```
A root user does not have to be named "root". whoami returns the first username with user ID 0. $USER contains the name of the logged in user, which can have user ID 0, but have a different name.

The only reliable program to check whether the account is logged in as root, or not:

id -u
I use -u for the effective user ID, not -r for the real user ID. Permissions are determined by the effective user ID, not the real one.

Tests
/etc/passwd contains the following usernames with user ID 0 in the given order:

rootx
root2
Logged in as root2, gives the next results:

whoami: rootx
echo $USER: root2 (this returns an empty string if the program was started in an empty environment, e.g. env -i sh -c 'echo $USER')
id -u: 0 As you can see, the other programs failed in this check, only id -u passed.
The updated script would looks like this:

#!/bin/bash
if ! [ $(id -u) = 0 ]; then
   echo "I am not root!"
   exit 1
fi

```
