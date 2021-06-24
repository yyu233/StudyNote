()

( list )
Placing a list of commands between parentheses causes a subshell environment to be created, and each of the commands in list to be executed in that subshell. Since the list is executed in a subshell, variable assignments do not remain in effect after the subshell completes.

{}

{ list; }
Placing a list of commands between curly braces causes the list to be executed in the current shell context. No subshell is created. The semicolon (or newline) following list is required.
