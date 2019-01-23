Bash is a script interpreter. 
To define interpreter: locate the full path to its executable binary using **which**, prefix it with **#!** and insert it as the 1st line of your script.    
**chmod +x [file]** Make a script file executable    
**>** redirect output    
**var = $(command)** command subsitution, the output of the command will be assigned to the user variable   
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

   
