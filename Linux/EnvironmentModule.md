Typically users initialize their environment when they log in by setting environment information for every application they will reference during the session. The Environment Modules package is a tool that simplify shell initialization and lets users easily modify their environment during the session with modulefiles.

Each modulefile contains the information needed to configure the shell for an application. Once the Modules package is initialized, the environment can be modified on a per-module basis using the module command which interprets modulefiles. Typically modulefiles instruct the module command to alter or set shell environment variables such as PATH, MANPATH, etc. modulefiles may be shared by many users on a system and users may have their own collection to supplement or replace the shared modulefiles.

Modules can be loaded and unloaded dynamically and atomically, in an clean fashion. All popular shells are supported, including bash, ksh, zsh, sh, csh, tcsh, fish, as well as some scripting languages such as perl, ruby, tcl, python, cmake and R.

Modules are useful in managing different versions of applications. Modules can also be bundled into metamodules that will load an entire suite of different applications.
