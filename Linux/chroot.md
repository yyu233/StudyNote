A chroot on Unix operating systems is an operation that changes the apparent root directory for the current running process and its children. A program that is run in such a modified environment cannot name (and therefore normally cannot access) files outside the designated directory tree. The term "chroot" may refer to the chroot(2) system call or the chroot(8) wrapper program. The modified environment is called a chroot jail.

## Common Uses ## 
* Testing and development   
A test environment can be set up in the chroot for software that would otherwise be too risky to deploy on a production system.
* Dependency control   
Software can be developed, built and tested in a chroot populated only with its expected dependencies. This can prevent some kinds of linkage skew that can result from developers building projects with different sets of program libraries installed.
* Compatibility   
Legacy software or software using a different ABI must sometimes be run in a chroot because their supporting libraries or data files may otherwise clash in name or linkage with those of the host system.
* Recovery   
Should a system be rendered unbootable, a chroot can be used to move back into the damaged environment after bootstrapping from an alternate root file system (such as from installation media, or a Live CD).
* Privilege separation   
Programs are allowed to carry open file descriptors (for files, pipelines and network connections) into the chroot, which can simplify jail design by making it unnecessary to leave working files inside the chroot directory. This also simplifies the common arrangement of running the potentially vulnerable parts of a privileged program in a sandbox, in order to pre-emptively contain a security breach. Note that chroot is not necessarily enough to contain a process with root privileges.
