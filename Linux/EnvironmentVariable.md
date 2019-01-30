## Environment Variable ##

Environment variable contains data that can be accessed and used globally by multiple applications. It eases setting configuration between applications and processess. 
They are inherited by any child shells and child processes.

Each process stores environment variables in /proc/$PID/environ  

Files defining environment variable globally: /etc/environment, /etc/profile, and shell specific configuration file.  

* /etc/environemnt is used by pam_env module

* /etc/profile is for login shell only. 

[Good Read](https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-a-linux-vps)
