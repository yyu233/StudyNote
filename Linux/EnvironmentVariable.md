## Environment Variable ##

Environment variable contains data that can be accessed and used globally by multiple applications. It eases setting configuration between applications and processess. 

Each process stores environment variables in /proc/$PID/environ  

Files defining environment variable globally: /etc/environment, /etc/profile, and shell specific configuration file.  

* /etc/environemnt is used by pam_env module

* /etc/profile is for login shell only. 
