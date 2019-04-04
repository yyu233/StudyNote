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
```
# Indirect Declaration
array[index]=value 

#Explicit Declaration
declare -a array 

#Compound Assignment 
array=(value1, value2, value3 ... valuen)

#All Elements of Array
array[@]
array[*]

#Print Elements of Array in Range 
echo ${array[@] starting_index: count}  

#Print Length of Array 
echo ${#array}   

#Search 
array[@]/regex/ 

#Search and Replace 
array[@]//regex/replacement 

#Delete Element 
unset array[index]

#Delete Whole Array 
unset array
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
