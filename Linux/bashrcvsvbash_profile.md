## .bashrc vs .bash_profile ##
.bashrc is a shell script that Bash runs whenever it is started interactively. It initializes an interactive shell session. You can put any command in that file that you could type at the command prompt.

You put commands here to set up the shell for use in your particular environment, or to customize things to your preferences. A common thing to put in .bashrc are aliases that you want to always be available

Contrast .bash_profile and .profile which are only run at the start of a new login shell. (bash -l) You choose whether a command goes in .bashrc vs .bash_profile depending on on whether you want it to run once or for every interactive shell start.
