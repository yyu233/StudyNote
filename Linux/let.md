Using let is similar to enclosing an arithmetic expression in double parentheses, for instance:

(( expr ))
However, unlike (( ... )), which is a compound command, let is a builtin command. As such, its individual arguments are subject to expansion by bash. For instance, let arguments will undergo globbing, pathname expansion, and word splitting unless you enclose the individual arguments in double quotes.

In the majority of situations, it's preferable to use double parentheses to evaluate arithmetic expressions. However, it's important to understand how let is different, and use it where appropriate.

Like all simple commands, let has its own environment. Variables used in expressions have scope local to the command. So, for instance, an argument to let will not be aware of other shell variables, unless they are exported.
