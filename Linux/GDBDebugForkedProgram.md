The follow-fork-mode setting controls whether GDB follows the parent or the child after the fork.

* set follow-fork-mode parent   
  After forking, debug the parent process. This is the default. 
* set follow-fork-mode child  
  After forking, debug the child process. 
* show follow-fork-mode     
    Displays the current setting of the follow-fork-mode
    
The set detach-on-fork setting controls whether the GDB keeps control of the other (not followed) process or leaves it to run.
    
* set detach-on-fork on   
    The process which is not followed (depending on the value of the follow-fork-mode) is detached and runs independently. This is the default. 
* set detach-on-fork off  
    GDB keeps control of both processes. The process which is followed (depending on the value of follow-fork-mode) is debugged as usual, while the other is suspended. 
* show detach-on-fork   
    Displays the current setting of detach-on-fork
