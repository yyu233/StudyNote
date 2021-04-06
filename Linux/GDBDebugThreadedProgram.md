Debugging Threaded Programs with GDB

GDB has the ability to debug individual threads, and to manipulate and examine them independently. To make GDB stop only the thread that is examined, use the commands set non-stop on and set target-async on. You can add these commands to the .gdbinit file. After that functionality is turned on, GDB is ready to conduct thread debugging.

GDB uses the concept of current thread. By default, commands apply to the current thread only.

* info threads  
    Displays a list of threads with their id and gid numbers, indicating the current thread. 
* thread id     
    Sets the thread with the specified id as the current thread. 
* thread apply ids command  
    Applies the command command to all threads listed by ids. The ids option is a space-separated list of thread ids. The special value all applies the command to all threads. 
* break location thread id if condition   
    Sets a breakpoint at a certain location with a certain condition only for the thread number id. 
* watch expression thread id    
    Sets a watchpoint defined by expression only for the thread number id. 
* command&  
    Executes the command command and returns immediately to the GDB prompt (gdb), continuing code execution in the background. 
* interrupt   
    Halts execution in the background. 
