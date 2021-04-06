The follow-fork-mode setting controls whether GDB follows the parent or the child after the fork.

* set follow-fork-mode parent   
  After forking, debug the parent process. This is the default. 
* set follow-fork-mode child  
  After forking, debug the child process. 
* show follow-fork-mode     
    Displays the current setting of the follow-fork-mode
