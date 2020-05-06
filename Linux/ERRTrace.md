errtrace Same as -E.

-E If set, any trap on ERR is inherited by shell functions, command substitutions, and commands executed in a sub‐ shell environment. The ERR trap is normally not inher‐ ited in such cases.

When errtrace is enabled, the ERR trap is also triggered when the error (a command returning a nonzero code) occurs inside a function or a subshell. Another way to put it is that the context of a function or a subshell does not inherit the ERR trap unless errtrace is enabled.
