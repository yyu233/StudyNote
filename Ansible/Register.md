
Another major use of variables is running a command and registering the result of that command as a variable. When you execute a task and save the return value in a variable for use in later tasks, you create a registered variable. 
Results will vary from module to module. Each module’s documentation includes a RETURN section describing that module’s return values. To see the values for a particular task, run your playbook with -v.

Registered variables are similar to facts, with a few key differences. Like facts, registered variables are host-level variables. However, registered variables are only stored in memory. (Ansible facts are backed by whatever cache plugin you have configured.) Registered variables are only valid on the host for the rest of the current playbook run. Finally, registered variables and facts have different precedence levels.

When you register a variable in a task with a loop, the registered variable contains a value for each item in the loop. The data structure placed in the variable during the loop will contain a results attribute, that is a list of all responses from the module. For a more in-depth example of how this works, see the Loops section on using register with a loop.
