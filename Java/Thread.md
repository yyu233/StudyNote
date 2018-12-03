## Thread 

Two ways to implement Thread: 
* Extend the Thread class
* Implement the Runnable interface

Use the second method if you want to extend from other base class since Java only allows inheritance from one base class. 

### Life Cycle of Thread

* Thread is created and has not started to run -> at runnable state, scheduler schedules time for thread to run

* Thread is blocked when it tries to access a section locked by another thread. 

* Thread is in waiting state until a timeout is complete. 

* Thread is in terminated state when it completes executiion and exits or an error occurs.


