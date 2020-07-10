Ansible module are hard to debug because:

modules are normally executed remotely
modules are executed by python subprocess (so we can not use pdb to debug)
So, you can debug the Ansible module in this way:

Make the module execute locally. This can be implemented either by setting the hosts to localhost or by using Ansible local_action module.
Write/Logging the variables you want to debug into a specific file. You can do this by using Python q library.
