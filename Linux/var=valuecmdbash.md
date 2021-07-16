In the Bourne shell, with:

var=value cmd
If cmd is a built-in (like read is), var remains set to value after cmd has finished. That's particularly critical with $IFS because in the Bourne shell, $IFS is used to split everything, not only the expansions. Also, if you remove the space character from $IFS in the Bourne shell, "$@" no longer works.

