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

Your title asks about ${array[@]} versus ${array[*]} but then you ask about $array[*] versus $array[@] which is a bit confusing. I'll answer both:

When you quote an array variable and use @ as a subscript, each element of the array is expanded to its full content regardless of whitespace (actually, one of $IFS) that may be present within that content. When you use the asterisk (*) as the subscript (regardless of whether it's quoted or not) it may expand to new content created by breaking up each array element's content at $IFS.

Here's the example script:
```
#!/bin/sh

myarray[0]="one"
myarray[1]="two"
myarray[3]="three four"

echo "with quotes around myarray[*]"
for x in "${myarray[*]}"; do
        echo "ARG[*]: '$x'"
done

echo "with quotes around myarray[@]"
for x in "${myarray[@]}"; do
        echo "ARG[@]: '$x'"
done

echo "without quotes around myarray[*]"
for x in ${myarray[*]}; do
        echo "ARG[*]: '$x'"
done

echo "without quotes around myarray[@]"
for x in ${myarray[@]}; do
        echo "ARG[@]: '$x'"
done
And here's it's output:

with quotes around myarray[*]
ARG[*]: 'one two three four'
with quotes around myarray[@]
ARG[@]: 'one'
ARG[@]: 'two'
ARG[@]: 'three four'
without quotes around myarray[*]
ARG[*]: 'one'
ARG[*]: 'two'
ARG[*]: 'three'
ARG[*]: 'four'
without quotes around myarray[@]
ARG[@]: 'one'
ARG[@]: 'two'
ARG[@]: 'three'
ARG[@]: 'four'
```
I personally usually want "${myarray[@]}". Now, to answer the second part of your question, ${array[@]} versus $array[@].

Quoting the bash docs, which you quoted:

The braces are required to avoid conflicts with the shell's filename expansion operators.
```
$ myarray=
$ myarray[0]="one"
$ myarray[1]="two"
$ echo ${myarray[@]}
one two
```
But, when you do $myarray[@], the dollar sign is tightly bound to myarray so it is evaluated before the [@]. For example:
```
$ ls $myarray[@]
ls: cannot access one[@]: No such file or directory
```
But, as noted in the documentation, the brackets are for filename expansion, so let's try this:
```
$ touch one@
$ ls $myarray[@]
one@
```
Now we can see that the filename expansion happened after the $myarray exapansion.

And one more note, $myarray without a subscript expands to the first value of the array:
```
$ myarray[0]="one four"
$ echo $myarray[5]
one four[5]
```
