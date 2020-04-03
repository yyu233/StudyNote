In order to use the code in a module, Python must be able to locate the module and load it into memory. The location information is stored as paths within Python. Whenever you request that Python import a module, Python looks at all the files in its list of paths to find it. The path information comes from three sources:


Environment variables: Python environment variables, such as PYTHONPATH, tells Python where to find modules on disk.

Current directory: You can change the current Python directory so that it can locate any modules used by your application.

Default directories: Even when you don’t define any environment variables and the current directory doesn’t yield any usable modules, Python can still find its own libraries in the set of default directories that are included as part of its own path information.
