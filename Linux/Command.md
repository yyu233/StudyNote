```
command [-pVv] command [arg ...]
              Run  command  with  args  suppressing  the normal shell function
              lookup. Only builtin commands or commands found in the PATH  are
              executed.   If the -p option is given, the search for command is
              performed using a default value for PATH that is  guaranteed  to
              find  all  of  the  standard  utilities.  If either the -V or -v
              option is supplied, a description of command is printed.  The -v
              option  causes a single word indicating the command or file name
              used to invoke command to be displayed; the -V option produces a
              more  verbose  description.  If the -V or -v option is supplied,
              the exit status is 0 if command was found, and  1  if  not.   If
              neither  option  is  supplied  and  an error occurred or command
              cannot be found, the exit status is 127.   Otherwise,  the  exit
              status of the command builtin is the exit status of command.  
   ```
