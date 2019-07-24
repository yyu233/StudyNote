The GIL does not prevent threading. All the GIL does is make sure only one thread is executing Python code at a time; control still switches between threads.

What the GIL prevents then, is making use of more than one CPU core or separate CPUs to run threads in parallel.

This only applies to Python code. C extensions can and do release the GIL to allow multiple threads of C code and one Python thread to run across multiple cores. This extends to I/O controlled by the kernel, such as select() calls for socket reads and writes, making Python handle network events reasonably efficiently in a multi-threaded multi-core setup.

What many server deployments then do, is run more than one Python process, to let the OS handle the scheduling between processes to utilize your CPU cores to the max. You can also use the multiprocessing library to handle parallel processing across multiple processes from one codebase and parent process, if that suits your use cases.

Note that the GIL is only applicable to the CPython implementation; Jython and IronPython use a different threading implementation (the native Java VM and .NET common runtime threads respectively).

To address your update directly: Any task that tries to get a speed boost from parallel execution, using pure Python code, will not see a speed-up as threaded Python code is locked to one thread executing at a time. If you mix in C extensions and I/O, however (such as PIL or numpy operations) and any C code can run in parallel with one active Python thread.

Python threading is great for creating a responsive GUI, or for handling multiple short web requests where I/O is the bottleneck more than the Python code. It is not suitable for parallelizing computationally intensive Python code, stick to the multiprocessing module for such tasks or delegate to a dedicated external library.
