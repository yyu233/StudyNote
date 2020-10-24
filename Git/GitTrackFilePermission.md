By default, git will update execute file permissions if you change them. It will not change or track any other permissions.

If you don't see any changes when modifying execute permission, you probably have a configuration in git which ignore file mode.

Look into your project, in the .git folder for the config file and you should see something like this:

[core]
    filemode = false
