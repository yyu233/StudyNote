Command line arguments would be insecure as most systems allow unprivileged users to read the full commandline of a process.

Environment variables are usually more secure than the commandline but some systems limit the total size of the environment. This could lead to truncation of the parameters if we hit that limit.

