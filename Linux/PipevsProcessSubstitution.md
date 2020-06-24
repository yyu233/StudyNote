```
A good way to grok the difference between them is to do a little experimenting on the command line. In spite of the visual similarity in use of the < character, it does something very different than a redirect or pipe.

Let's use the date command for testing.

$ date | cat
Thu Jul 21 12:39:18 EEST 2011
This is a pointless example but it shows that cat accepted the output of date on STDIN and spit it back out. The same results can be achieved by process substitution:

$ cat <(date)
Thu Jul 21 12:40:53 EEST 2011
However what just happened behind the scenes was different. Instead of being given a STDIN stream, cat was actually passed the name of a file that it needed to go open and read. You can see this step by using echo instead of cat.

$ echo <(date)
/proc/self/fd/11
When cat received the file name, it read the file's content for us. On the other hand, echo just showed us the file's name that it was passed. This difference becomes more obvious if you add more substitutions:

$ cat <(date) <(date) <(date)
Thu Jul 21 12:44:45 EEST 2011
Thu Jul 21 12:44:45 EEST 2011
Thu Jul 21 12:44:45 EEST 2011

$ echo <(date) <(date) <(date)
/proc/self/fd/11 /proc/self/fd/12 /proc/self/fd/13
It is possible to combine process substitution (which generates a file) and input redirection (which connects a file to STDIN):

$ cat < <(date)
Thu Jul 21 12:46:22 EEST 2011
It looks pretty much the same but this time cat was passed STDIN stream instead of a file name. You can see this by trying it with echo:

$ echo < <(date)
<blank>
Since echo doesn't read STDIN and no argument was passed, we get nothing.

Pipes and input redirects shove content onto the STDIN stream. Process substitution runs the commands, saves their output to a special temporary file and then passes that file name in place of the command. Whatever command you are using treats it as a file name. Note that the file created is not a regular file but a named pipe that gets removed automatically once it is no longer needed.

```
