## Standard Error ## 

In bash, standard error can be redirected on the command line. Redirecting stderr can be useful if you need to capture any error messages to a separate log file, or hide the error messages entirely.

For example, consider the following find command:
```
 find / -iname '*something*'
 /usr/share/doc/something
 /usr/share/doc/something/examples/something_random
 find: `/run/udisks2': Permission denied
 find: `/run/wpa_supplicant': Permission denied
 /usr/share/something
 /usr/games/something
```
We're getting errors because find is trying to search a few system directories that we don't have permission to read. The lines that say "Permission denied" are error messages, and were written to stderr. The other lines were written to stdout (standard output). By default, they both display on the terminal.

To hide stderr, we can redirect them by referencing standard error's file descriptor number, 2, and a "redirect output" operator, >.

```
 find / -iname '*something*' 2>/dev/null
 /usr/share/doc/something
 /usr/share/doc/something/examples/something_random
 /usr/share/something
 /usr/games/something
 ```
