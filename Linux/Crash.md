Crash is a tool for interactively analyzing the state of the
       Linux system while it is running, or after a kernel crash has
       occurred and a core dump has been created by the netdump,
       diskdump, LKCD, kdump, xendump kvmdump or VMware facilities.  It
       is loosely based on the SVR4 UNIX crash command, but has been
       significantly enhanced by completely merging it with the gdb(1)
       debugger. The marriage of the two effectively combines the
       kernel-specific nature of the traditional UNIX crash utility with
       the source code level debugging capabilities of gdb(1).

       In the dumpfile form, both a NAMELIST and a MEMORY-IMAGE argument
       must be entered.  In the live system form, the NAMELIST argument
       must be entered if the kernel's vmlinux file is not located in a
       known location, such as the /usr/lib/debug/lib/modules/<kernel-
       version> directory.

       The crash utility has also been extended to support the analysis
       of dumpfiles generated by a crash of the Xen hypervisor.  In that
       case, the NAMELIST argument must be that of the xen-syms binary.
       Live system analysis is not supported for the Xen hypervisor.

       The crash utility command set consists of common kernel core
       analysis tools such as kernel stack back traces of all processes,
       source code disassembly, formatted kernel structure and variable
       displays, virtual memory data, dumps of linked-lists, etc., along
       with several commands that delve deeper into specific kernel
       subsystems.  Appropriate gdb commands may also be entered, which
       in turn are passed on to the gdb module for execution.  If
       desired, commands may be placed in either a $HOME/.crashrc file
       and/or in a .crashrc file in the current directory.  During
       initialization, the commands in $HOME/.crashrc are executed
       first, followed by those in the ./.crashrc file.