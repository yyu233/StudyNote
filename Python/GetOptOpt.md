```
getopt.getopt method
This method parses command line options and parameter list. Following is simple syntax for this method −

getopt.getopt(args, options, [long_options])
Here is the detail of the parameters −

args − This is the argument list to be parsed.

options − This is the string of option letters that the script wants to recognize, with options that require an argument should be followed by a colon (:).

long_options − This is optional parameter and if specified, must be a list of strings with the names of the long options, which should be supported. Long options, which require an argument should be followed by an equal sign ('='). To accept only long options, options should be an empty string.

This method returns value consisting of two elements: the first is a list of (option, value) pairs. The second is the list of program arguments left after the option list was stripped.

Each option-and-value pair returned has the option as its first element, prefixed with a hyphen for short options (e.g., '-x') or two hyphens for long options (e.g., '--long-option').

```
