Bash is a script interpreter. 
To define interpreter: locate the full path to its executable binary using **which**, prefix it with **#!** and insert it as the 1st line of your script.    
**chmod +x [file]** Make a script file executable    
**>** redirect output    
**var = $(command)** command subsitution, the output of the command will be assigned to the user variable   
**=** recursively expanded variable
```
  x=foo
  y="$(x) bar"
  x=choc
  echo y #print choc bar
```
**:=** simple expanded variable
```
  x:=foo
  y:="$(x) bar"
  x:=choc
  echo y #print foo bar
```

  
**#** comment starts with #    
**${parameter}** parameter expansion    
**"$VAR"** parameter expansion
X=hello world # error 
X="hello world" #ok

```
  if condition 1
    then statement 1
  eif condition 2
    then statement 2
  ...
  fi
```

```
  A=1
  B=2
  X=""
  if [$A -lt $B] 
    then echo "\$A={$A}, \$B={$B}, \$A is less than \$B" 
  fi 
  
  if [-n "$X"]; then 
    echo "It is non-mepty"
  fi
  
  if [-e "$HOME/file"]; then
    echo "file exists" 
    if [-L "$HOME/file"]; then 
      echo "file is symbolic link"
    eif [-f "$HOME/file"]; then
      echo "file is regular file"
    fi
  else
    echo "file does not exist"
  fi
```
```
$?       Expands to the exit status of the most recently executed foreground pipeline
$@       All arguments passed to the script
$#       Number of arguments passed to shell 
$*       String containing all the arguments passed to shell
```

```
$()     command substitution. run the command inside parentheses and substitute. 
```

Case Statements
--------------------
```
          case  $variable-name  in
                pattern1)       
     		    command1
                    ...
                    ....
                    commandN
                    ;;
                pattern2)
     		    command1
                    ...
                    ....
                    commandN
                    ;;            
                patternN)       
     		    command1
                    ...
                    ....
                    commandN
                    ;;
                *)              
          esac 
```

For Loop
----------------
```
for a in n 
do 
   ....
done
```
Test Operators
--------------------------------
|Operator|Produce true if| 
|--------|---------------|
|-n | operand non-zero length |
|-z| operand has zero length |
|-d |there exists a directory whose name is operand |
|-f |there exists a file whose name is operand |
|-eq| operands are integers and equal|
|-neq| the opposite of equal| 
|=| the operands are strings and equal|
|!=| the opposite of = |
|-lt | operand 1 is strictly less than operand 2. Operands are integers |
|-gt| operand 1 is strictly greater than operand 2. Operands are integers |
|-le| operand 1 is less than or equal to operand 2. Operands are integers |
|-ge| operand 1 is greater than or equal to operand 2. Operands are integers|



Array
---------------------------------
Bash supports one-dimensional numerically indexed and associative arrays types. Numerical arrays are referenced using integers, and associative are referenced using strings.

Numerically indexed arrays can be accessed from the end using negative indices, the index of -1 references the last element. The indices do not have to be contiguous.

Unlike most of the programming languages, Bash array elements don’t have to be of the same data type. You can create an array that contains both strings and numbers.
```
# Indirect Declaration
array[index]=value 

#Explicit Declaration
declare -a array 

#Declare Associative Array
declare -A array

#Compound Assignment 
array=(value1, value2, value3 ... valuen)

#All Elements of Array
array[@]
array[*]

#Print Elements of Array in Range 
echo ${array[@]:starting_index: count}  

#Print Length of Array 
echo ${#array[@]}   

#Search 
array[@]/regex/ 

#Search and Replace 
array[@]//regex/replacement 

#Delete Element 
unset array[index]

#Delete Whole Array 
unset array

#Add Elememt
array+=("$var") #note: array+="$var$" this will append value of var to the lowest index element in array     
array=("${array[@]}" "$var")   
```

Parameter Substitution 
--------------------------
```
pattern=1*3
var=1234536
echo ${var#$pattern} #strip out shortest match from left, print 4536 
echo $(var##$pattern} #strip out longest match from left, print 6 

var2=12115123
echo ${var%$pattern} #strip out shortest match from right, print 12115
echo ${var%%$pattern} #strip out longest match from right, print nothing 
```

Scope
-------------------------
No scope.    
Create a shell script called foobar.sh
```
#!/bin/sh 

foobar() 
{
  echo "Arguments values are: $@"
  x=2
}

echo "Script argumemts values are: $@"
x=1
echo "x is $x"
foobar 1 2 3
echo "x is $x"
```
./foobar.sh a b c    
output: 
```
Script arguments values are: a b c
x is 1
Arguments values are: 1 2 3
x is 2
```
local visibility

```
func()
{
  local local_var=0
  global_var=1
}
echo "$local_var"  # not visible

echo "$global_var" # not visible before func is called

func
echo "$global_var" # visible
```

Configure shell options and positional parameters
-------------------------------------------------

```
 set -x #Print commands and their arguments as they are executed 
 
 set -e #Exit immediately if a command exits with a non-zero status
 
 set -u #Treat unset variables as an errror when subsituting.
 
 set -o pipefail #pipe only return the exist status of last command. We can use this set command to make pipe break if any command failed.
```

Subshell
---------------------------------------------------
subshells (written with parentheses) are convenient ways to group commands. A common example is to temporarily move to a different working directory, e.g.

```
      # do something in current dir
      (cd /some/other/dir && other-command)
      # continue in original dir
```

Automate Combination of Files
--------------------------------
```
mv foo.{txt,pdf} some-dir
```

Parameter Expansion
----------------
|Expression | Parameter Set and Not Null | Parameter Set But Null | Parameter Unset| 
|---------|--------------------------|-----------------|---------------------------|
|${parameter:-word} | substitute parameter| substitute word| substitute word|
|${parameter-word}|substitute parameter| substitute null| substitute word|
|${parameter:=word}|substitute parameter | assign word | assign word|
|${parameter=word} |substitute parameter|substitute null | assign word|
|${parameter:?word}|substitute parameter | error exit | error exit|
|${parameter?word}|substitute parameter | substitute null | error exit|
|${parameter:+word}|substitute word|substitute null|substitute null|
|${parameter+word}|substitute word| substitute word| substitute null| 

```
var=foo
echo ${var/f/F}  # FOO
echo ${var//o/O} #fOO replace all o
echo ${var:0:2} # fo
echo ${var::2}  # fo
echo ${var::-1} # fo
echo ${var:(-1)} # o
echo ${var:(-2):1} # o
echo ${var%oo} # f  remove suffix
echo ${var#f} # remove prefix
echo ${var/%oo/ar} # replace suffix
echo ${var/#f/b} # replace prefix

path=/path/foo/bar/foobar.sh
echo ${path#*/} # path/foo/bar/foobar.sh
echo ${path##*/} # foobar.sh

```
Source command
----------------
The source command can be used to load any functions file into the current shell script or a command prompt.
It read and execute commands from given FILENAME and return.
The pathnames in $PATH are used to find the directory containing FILENAME. If any ARGUMENTS are supplied, they become the positional parameters when FILENAME is executed.
```
source filename [arguments]
source functions.sh
source /path/to/functions.sh arg1 arg2
source functions.sh WWWROOT=/apache.jail PHPROOT=/fastcgi.php_jail
```

Regex Match
----------------------------
The ~ is actually part of the operator =~ which performs a regular expression match of the string to its left to the extended regular expression on its right.
```
[[ "string" =~ pattern ]]
```
Note that the string should be quoted, and that the regular expression shouldn't be quoted.

Print Sequence
-----------------------------
```
 echo {0..10}
 
 echo {0..10}{a..z}
```

Outgoing Grouping
--------------------

```
{ echo "a" ; ls } > output.log  # print all output from commands into file

```

Redirection
--------------------------
```
  read <<< string   # <<< denotes here string
  
  cat << file 
  
  # You can use any string as a delimiting identifier, the most commonly used are EOF or END.
  # If the delimiting identifier is unquoted, the shell will substitute all variables, commands and special characters before passing     # the here-document lines to the command.
  # Appending a minus sign to the redirection operator <<-, will cause all leading tab characters to be ignored. This allows you to use   # indentation when writing here-documents in shell scripts. Leading whitespace characters are not allowed, only tab.

```

Containing String
----------------------------

```
[ "$STR1" == *"$STR2"* ]

[[ "$STR1" ~= .*"$STR2".* ]]

```

Unset Multiple Variables
----------------------------
```
unset($var1, $var2 ...)

```

ERRTRACE
----------------------
```
errtrace Same as -E.

-E If set, any trap on ERR is inherited by shell functions, command substitutions, and commands executed in a sub‐ shell environment. The ERR trap is normally not inher‐ ited in such cases.

When errtrace is enabled, the ERR trap is also triggered when the error (a command returning a nonzero code) occurs inside a function or a subshell. Another way to put it is that the context of a function or a subshell does not inherit the ERR trap unless errtrace is enabled.
```

Interpolate control character
-----------------------------
```
 printf %q <args>  # if args contain control characters like '\t', 'n', %q will not make shell interpret them but rather insert the literal value into the line on console.
````
\*
--------------------
```
The shell is expanding * to all files in the current directory that do not start with a dot. This is the same rule that ls uses by default (by convention, files whose names start with a dot are considered "hidden" in Unix).
```

Case Modification
---------
```
${PARAM^}
${PARAM^^}
${PARAM,}
${PARAM,,}
${PARAM~}
${PARAM~~}
The ^ changes the first character to uppercase. The , to lower case. When use the double form, all chars are changed.
```

{}
---------
You can also use { ... } to group the output from several commands into one big blob. The command:


echo "I found all these PNGs:"; find . -iname "*.png"; echo "Within this bunch of files:"; ls > PNGs.txt
will execute all the commands but will only copy into the PNGs.txt file the output from the last ls command in the list. However, doing


{ echo "I found all these PNGs:"; find . -iname "*.png"; echo "Within this bunch of files:"; ls; } > PNGs.txt
creates the file PNGs.txt with everything, starting with the line “I found all these PNGs:“, then the list of PNG files returned by find, then the line “Within this bunch of files:” and finishing up with the complete list of files and directories within the current directory.

Notice that there is space between the braces and the commands enclosed within them. That’s because { and } are reserved words here, commands built into the shell. They would roughly translate to “group the outputs of all these commands together” in plain English.

Also notice that the list of commands has to end with a semicolon (;) or the whole thing will bork.
