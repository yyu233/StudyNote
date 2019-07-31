## Environment Variable ##

Environment variable contains data that can be accessed and used globally by multiple applications. It eases setting configuration between applications and processess. 
They are inherited by any child shells and child processes.

Each process stores environment variables in /proc/$PID/environ  

Files defining environment variable globally: /etc/environment, /etc/profile, and shell specific configuration file.  

* /etc/environemnt is used by pam_env module

* /etc/profile is for login shell only. 

See a list of environment variables:  **printenv** or **env**   

**printenv  VAR**  can print indiviual values.

**env  VAR=value** can modify variable values.

## Commonly Used Variables ##

|System Variable | Meaning |
|---------|-------|
|BAHS_VERSION| Holds the version of this instance of bash|
|HOSTNAME| The name of your computer|
|CDPATH|The search path for the cd command|
|HISTFILE| The name of the file in which command history is saved |
|HISTFILESIZE| The maximum number of lines contained in the history file|
|HISTSIZE|The number of commands to remember in the command history.The dafault value is 500|
|HOME|The home directory of the current user|
|IFS| The Internal Field Seperator that is used for word splitting after expansion and to split lines into words with the read builtin command. The default value is <space><tab><newline>|
|PATH| The search path for commands. It is a colon-separated list of dictiories in which the shell looks for commands|
  |TIMEOUT|The default timeout for the read builtin command. Also in an interactive shell, the value is interpreted as the number of seconds to wait for input after issuing the command. If not input provided it will logout user.|
  |TERM| Your login terminal type|
  |SHELL|Set path to login shell|
  |DISPLAY| Set X display name|
  |EDITOR|Set name of default text editor|

 
[Good Read](https://www.digitalocean.com/community/tutorials/how-to-read-and-set-environmental-and-shell-variables-on-a-linux-vps)
