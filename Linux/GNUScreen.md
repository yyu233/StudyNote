|Action| Command|
|----|-----|
|Start a new session with session name | screen -S \<name> |
|List running session| screen -ls |
|Attach to a running session | screen -x|
|Attach to a session name| screen -r \<name>| 
|Detach | Ctrl-a d |
|Deatach and logout | Ctrl-a D D|
|Create a new window| Ctrl-a c|
|Change to window by number| Ctrl-a \<number>|
|Change to next window| Ctrl-a n|
|Change to previous window| Ctrl-a p|
|See window list| Ctrl-a "|
|Split window horizontally|Ctrl -a S|
|Split window vertically| Ctrl -a \| |
|Jump to next display|Ctrl -a tab|
|Remove current region| Ctrl-a X|
|Send a command to a names session|screen -S \<name> -X \<command>| 
