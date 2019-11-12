When they are not quoted, $* and $@ are the same. You shouldn't use either of these, because they can break unexpectedly as soon as you have arguments containing spaces or wildcards.

"$*" expands to a single word "$1c$2c...". Usually c is a space, but it's actually the first character of IFS, so it can be anything you choose.

The only good use I've ever found for it is:

```
join arguments with comma (simple version)

join1() {
    typeset IFS=,
    echo "$*"
}

join1 a b c   # => a,b,c
join arguments with the specified delimiter (better version)

join2() {
    typeset IFS=$1   # typeset makes a local variable in ksh (see footnote)
    shift
    echo "$*"
}

join2 + a b c   # => a+b+c
"$@" expands to separate words: "$1" "$2" ...
```
This is almost always what you want. It expands each positional parameter to a separate word, which makes it perfect for taking command line or function arguments in and then passing them on to another command or function. And because it expands using double quotes, it means things don't break if, say, "$1" contains a space or an asterisk (*).
