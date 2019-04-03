[ x$1 = x ]
Only makes sense in zsh. That compares the concatenation of x with the first argument of the script to x. So the [ command returns true if $1 is empty or not provided.

[ $1 = "" ]
Wouldn't work because, in zsh when an empty variable is not quoted in list contexts, it expands to no argument at all instead of an empty argument, so if $1 were unset or empty, the [ command would only receive as arguments [, =, the empty string and ] which it couldn't make sense out of.  [ -z "$1" ] or [ "$1" = "" ] would be OK though like in POSIX shells.

In Bourne-like/POSIX shells, [ x$1 = x ] does not make sense. That's the split+glob operator somehow applied to the concatenation of x and the first argument of the script hoping that the result and = and x, and ] make up a valid test expression for the [ command.

For instance, if the script was passed one " = x -o x =", [ would receive those arguments: [, x, =, x, -o, x, =, x, ], which [ would understand as comparing x with x and x with x and return true.

If $1 were "* *", then the shell would pass to the [ command the list of files in the current directory whose name starts with x (the glob expansion of x*), then the list of non-hidden files (expansion *)... which [ is unlikely to be able to make any sense out of. The only cases where that would do anything sensible is if $1 does not contain wildcard or blank characters.

Now, what you sometimes find is code like:

[ "x$1" = x ]
That is used to test if $1 is empty or unset.

The normal way to test for an empty or unset variable is:

[ -z "$1" ]
But that fails for some values of $1 like = in some (non-POSIX) [ implementations like the builtin one in the Bourne shell as found as /bin/sh on Solaris 10 and before or some old versions of dash (up to 0.5.4) or the sh of some BSDs.

That's because [ sees [, -z, =, ] and complains about missing arguments to the = binary operator instead of understanding it as the -z unary operator applied to the = string.

Similarly, [ "$1" = "" ] fails for some implementations of [ if $1 is ! or (.

In those shell/[ implementations:

[ "x$1" = x ]
is always a valid test regardless of the value of $1, so are:

[ "" = "$1" ]
and:

[ -z "${1:+x}" ]
and

case $1 in "") ...; esac
Of course, if you want to check that no argument is provided, you'd do:

[ "$#" -eq 0 ]
That is, you check the number of arguments passed to the script.

Note that nowadays, [ -z "$var" ] is clearly specified by POSIX and cannot fail in conformant [ implementations (and bash's [ is and has been for decades). So you should be able to rely on it in POSIX sh or bash scr
