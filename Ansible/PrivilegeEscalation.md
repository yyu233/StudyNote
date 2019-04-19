## Privilege Escalation ## 

Switch to user from the login user.   

**directive**
* become: toggle privilege escalation, override default ansible.cfg    
* become_user: the user you will switch to
* become_method: privilege escalatioin method, override default ansible.cfg   

If you need to specify a password to sudo, run ansible-playbook with --ask-become-pass or when using the old sudo syntax --ask-sudo-pass (-K). If you run a become playbook and the playbook seems to hang, it’s probably stuck at the privilege escalation prompt. Just Control-C to kill it and run it again adding the appropriate password.

