In fork, every new process should have it’s own memory/address space, hence a longer startup and stopping time.
If you fork, you have two independent processes which need to talk to each other in some way. This inter-process communication is really costly.
When the parent exits before the forked child, you will get a ghost process. That is all much easier with a thread. You can end, suspend and resume threads from the parent easily. And if your parent exits suddenly the thread will be ended automatically.
In-sufficient storage space could lead the fork system to fail.
