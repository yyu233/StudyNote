## CLISH ##

CLISH stands for Command Line Interface Shell.    

Command line and menu are defined by XML files.  When CLISH is launched, it starts searching files in the CLISH_PATH environment variable (/etc/clish:~/.clish) for any fils with ".xml" extension. These XML files will build up the CLISH tree for current user. 

The shell will guide user through the available commands, and will provide context sensitive help and auto-completion. A sub-shell will be spawned to interpret the <ACTION> part of XML file when a command is entered. 
