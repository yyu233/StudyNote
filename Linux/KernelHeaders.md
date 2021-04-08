

As stated, header files define interfaces to functions as well as structures used by programs.

In the case of the kernel header files, these functions and structures are within the kernel itself.

If you are building a complete kernel, then, obviously, you need the complete source files, not just the headers. However, if you are compiling a device driver or other loadable module which links into the kernel then you only need the header files, so can save space by not installing the full sources.

The separation of packages so that you can install just the header files is partly historical as the difference in disk usage used to be a significant consideration when disks were smaller. These days, having the entire source on disk (unnecessarily) would not be a major disk space consideration.
