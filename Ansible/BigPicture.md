## Master Slave ## 
1. Install Ansible on machine (master). 
2. Ansible SSH to other machine (slave). When Ansible manages other machine, no software will be left installed or running on other machine. 

## Configure Ansible ##
```/etc/ansible```

## Hierarchy ##
Playbook   
&ensp;&ensp;Roles   
&ensp;&ensp;&ensp;&ensp;Tasks    
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Modules

## Playbook ## 
The goal of a play is to map a group of hosts to some well defined roles, represented by things ansible calls tasks. At a basic level, a task is nothing more than a call to an ansible module.

By composing a playbook of multiple ‘plays’, it is possible to orchestrate multi-machine deployments, running certain steps on all machines in the webservers group, then certain steps on the database server group, then more commands back on the webservers group, etc.
