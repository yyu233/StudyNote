1. Take the value of the variable, which is a string. If the variable is not defined, use the empty string.
2. If the construct includes a transformation, apply it. For example, if the construct is ${VARIABLE#TEXT}, and the value of the variable begins with TEXT, remove TEXT from the beginning of the value.
3. If the context calls for a single word (for example within double quotes, or in the right-hand side of an assignment, or inside a here document), stop here. Otherwise continue with the next steps.
4. Split the value into separate words at each sequence of whitespace. (The variable IFS can be changed to split at characters other than whitespace.) The result is thus no longer a string, but a list of strings. This list can be empty if the value contained only whitespace.
5. Treat each element of the list as a file name wildcard pattern, i.e. a glob. If the pattern matches some files, it is replaces by the list of matching file names, otherwise it is left alone.

For example, suppose that the variable foo contains a* b* c* and the current directory contains the files bar, baz and paz. Then ${foo#??} is expanded as follows:

1. The value of the variable is the 8-character string a* b* c*.
2. #?? means strip off the first two characters, resulting in the 6-character string  b* c* (with an initial space).
3. If the expansion is in a list context (i.e. not in double quotes or other similar context), continue.
4. Split the string into whitespace-delimited words, resulting in a list of two-strings: b* and c*.
5. The string b*, interpreted as a pattern, matches two files: bar and baz. The string c* matches no file so it is left alone. The result is a list of three strings: bar, baz, c*.
