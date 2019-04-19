## Shell Type ##

Three types of shell: 

* a login shell
* an interactive shell 
* a non-interactive shell  

### Login Shell ###  

put environment variables in: 
* .profile
* .bash_profile 
* .bash_login 

### Interactive Bash Shell ### 

put environment variables in: 
* bash.rc 

### Non-interactive Shell ### 
run from script. shell cannot interact with user. bash.rc and .profile are not executed.    


### Detect shell type 
``` [[ $- != *i*]] && echo "non-interactive" || echo "interactive" ```   

[[ $- != *i* ]]: $- means shell flag. It checks if the interactive flag is set. The [[ and ]] make it a boolean. 

default flags: 

* h: this tells bash to remember the locations of commands it has found through querying your PATH
* i: interactive
* m: monitor. enable job control 
* B: brace expansion 
* H: enable you to rerun a command from your history by prefacing its number with an exclamation point
