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
