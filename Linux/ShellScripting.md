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
```

Array
```
# Indirect Declaration
ARRAY[INDEX]=value 

#Explicit Declaration
declare -a ARRAY 

#Compound Assignment 
ARRAY=(value1, value2, value3 ... valuen)

#All Elements of Array
ARRAY[@]
ARRAY[*]

#Print Elements of Array in Range 
echo ${ARRAY[@] STARTING_INDEX : COUNT}  

#Print Length of Array 
echo ${#ARRAY}   

#Search 
ARRAY[@]/REGEX/ 

#Search and Replace 
ARRAY[@]//REGEX/REPLACEMENT 

#Delete Element 
unset ARRAY[INDEX]

#Delete Whole Array 
unset ARRAY
```

Parameter Substitution 
```
PATTERN=1*3
VAR=1234536
echo ${VAR#$PATTERN} #strip out shortest match from left, print 4536 
echo $(VAR##$PATTERN} #strip out longest match from left, print 6 

VAR2=12115123
echo ${VAR%$PATTERN} #strip out shortest match from right, print 12115
echo ${VAR%%$PATTERN} #strip out longest match from right, print nothing 
```
