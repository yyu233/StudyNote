## /dev/null ## 

The null device is typically used for disposing of unwanted output streams of a process, or as a convenient empty file for input streams

This entity is a common inspiration for technical jargon expressions and metaphors by Unix programmers, e.g. "please send complaints to /dev/null", "my mail got archived in /dev/null", and "redirect to /dev/null"—being jocular ways of saying, respectively: "don't bother sending complaints", "my mail was deleted", and "go away". The iPhone Dev Team commonly uses the phrase "send donations to /dev/null", meaning they do not accept donations.The fictitious person name "Dave (or Devin) Null" is sometimes similarly used (e.g., "send complaints to Dave Null").

### Why invent /dev/null ### 

``` cat file | null ```  would have a lot of overhead, first in setting up a pipe, spawning a process, executing "null" in the new process, etc. Also, null itself would use quite a bit of CPU in a loop reading bytes into a buffer that is later just discarded... The implementation of /dev/null in the kernel is just more efficient that way. Also, what if you want to pass /dev/null as an argument, instead of a redirection? (You could use <(...) in bash, but that's even way heavier handed!
