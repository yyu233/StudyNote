There are actually two types of address resolutions performed by klogd.

* Static translation, which uses the System.map file.
* Dynamic translation, which is used with loadable modules. These translations don't use System.map and is therefore not relevant to this discussion, but I'll describe it briefly anyhow:

Klogd Dynamic Translation

Suppose you load a kernel module which generates an oops. An oops message is generated, and klogd intercepts it. It is found that the oops occured at d00cf810. Since this address belongs to a dynamically loaded module, it has no entry in the System.map file. klogd will search for it, find nothing, and conclude that a loadable module must have generated the oops. klogd then queries the kernel for symbols that were exported by loadable modules. Even if the module author didn't export his symbols, at the very least, klogd will know what module generated the oops, which is better than knowing nothing about the oops at all.
