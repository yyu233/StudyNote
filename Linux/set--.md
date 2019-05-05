Text: 1.2.3  version1

```set -- $(<text)```

That command combines two rather special tricks...

set --

Usually set is used to configure shell options (see the man page of your shell). A special case is set --. This is used to set the positional parameters. Unfortunately I have forgotten what that was about but I once read about a problem which could not be solved well by other means.

$(< file)

$(command) is command subsitution: The shell collects the output on stdout and replaces $(command) by that output when executing the command line. If you need the content of a file you could do this: $(cat file). $(< file) is just a short version of that, saving an unnecessary process (cat).

Just to clarify: set 1.2.3 version1 would also set $1 to 1.2.3 and $2 to version1. The -- tells set to stop accepting flags. That way, if the file text contained something along the lines of -k version1, set would not confuse the first field of the file's text for a flag.
