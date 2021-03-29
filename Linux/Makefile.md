## Makefile ##

### Syntax of Rule ###

```
  target: prerequisite
  <tab>   recipe
```
A target can be executable, object file, and **action**. 

Tab for each line of recipe to distinguish recipe from other lines. 

Make carries out the recipe on prerequisite to create or update the target.

Recompilation must be done if any of the prerequisites is more recent than the object file or the object file does not exist.   
Simple Makefile

``` include ``` directive tells *make* to suspend readig the current makefile and read other makefile before continuing. 

``` -include ``` directibe will ignore non-existent makefile without throwing warning or error. 

Normal method for preventing  *make* from implicit rule look up for efficieny: use empty recipe.   

One target can be only associated with one recipe in one makefile.   

GNU make works in 2 phases: read-in phase and target-update phase.

The default goal is the first target of the first rule of the first makefile. If the first rule has multiple targets, only the first one is default goal. A target starting with period is not a default goal and a target defining a pattern is not either.   

$${var} escapes $ so that ${var} is passed to shell. 

```
  foobar.o: foobar.h
  <tab>  cc -c foobar.c
```

Use variable to store a list of file names

```
  objects = object1.o, object2.o\
            object3.o, object4.o
  foobar: $(objects)
  <tab>   cc -o foobar $(objects)
```

Use implicit rule to automatically update .o file from .c file

```
  obejects = object1.o, object2.o\
             object3.o, object4.o
  foobar: $(objects)
  <tab>   cc -o foobar $(objects)
  
  object1.o: object1.h
  object2.o: object2.h
  object3.o: object3.h
  object4.o: object4.h
```
If you write a rule whose recipe never creates a target file, this rule will always be executed every time when the target file does not exist. If the target file exists, for example a file named *clean*, since the clean does not have prerequisites in the rule, clean would always be considered as updated, and the rule will not be executed.
Clean: 

```
  .PHONY: clean
  clean: 
        -rm  foobar $(objects)
```

A phony target is not a real file, instead it is the name of the recipe when you explicitly request for execution. A phony target is used for avoiding file name conflict or improve performance (implicit rule search is skipped). It should not be a prerequisite of a real target file, otherwise its recipe will be run every time make goes to update that file. 


```
  all: prog1, prog2, prog3
  .PHONY: all
  
  prog1: prog1.o
  <tab>  cc -o prog1 prog1.o
  
  prog2: prog2.o
  <tab>  cc -o prog2 prog2.o
  
  prog3: prog3.o
  <tab>  cc -o prog3 prog3.o
```

Makefile contains explicit rule, implicit rule, variable definitoin, directive and comments. 

```
  include *.mk   
  -include *.mk  #ignore errors for file not exists or cannot be remade
```

Make search for implicit rule for each target without recipe.   
Explicit rule does not influence implict rule search. For example:
```
  foo.o: foo.p 
```

If foo.c exists, then the implicit rule to make foo.o by C compiler is used. 

Set default goal: 

```
# Note that assigning more than one target name to .DEFAULT_GOAL is invalid and will result in an error.

.DEFAULT_GOAL:= foo
```

### Secondary Expansion ###

```
.SECONDEXPANSION:
ONEVAR = onefile
TWOVAR = twofile
myfile: $(ONEVAR) $$(TWOVAR)
```

If ``` .SECONDEXPANSION ``` is defined, then between 1st phase and 2nd phase, variables defined under ``` .SECONDEXPANSION ``` will be expanded second time. $$ is escaped variable. 1st time expansion, TWOVAR is not recognized as variable until 2nd time.   

### Pattern Rules ### 
The target of a pattern rule contains the character '%' which can match any nonempty **substring** .    
'%' in a prerequisite of a pattern rule stands for the same stem that was matched by the '%' in the target.    
A pattern rule need not habe any prerequisites that contain'%', or any prerequisites at all.   

### Substitution on Variable ### 
```
VAR=a.h
SUB=$(VAR:.h=.o) #change a.h to a.o
```

### Recursive Make ### 
```
subsystem: 
  cd subdir && $(MAKE)
```
or 

```
subsystem:
  $(MAKE) -C subdir
```

### Normal Prerequisite & Order-only Prerequisite ### 

Normal Prerequisite: 
1. Impose an order for the recipe invocation: recipe of all prerequisites run first before recipe of target. 
2. Impose a dependency relationship: any prerequisite is newer than the target (check the timestamp of the file creation), target must be rebuilt. 

Consider an example where your targets are to be placed in a separate directory, and that directory might not exist before make is run. In this situation, you want the directory to be created before any targets are placed into it but, because the timestamps on directories change whenever a file is added, removed, or renamed, we certainly don’t want to rebuild all the targets whenever the directory’s timestamp change.

``` targets: normal-prerequisites | order-only-prerequisites ```

Order-only Prerequisite: 
1. Impose an order for the recipe invocation: recipe of all prerequisites run first before recipe of target. 

### Error Message ###
[Reference](https://www.gnu.org/software/make/manual/make.html#Error-Messages)

### Parallel Execution ### 
``` make -j ``` or ``` make --jobs ```     
If the ‘-j’ option is followed by an integer, this is the number of recipes to execute at once; this is called the number of job slots. If there is nothing looking like an integer after the ‘-j’ option, there is no limit on the number of job slots. The default number of job slots is one, which means serial execution (one thing at a time).

```make -l ```     
set load limit: more precisely, when make goes to start up a job, and it already has at least one job running, it checks the current load average; if it is not lower than the limit given with ‘-l’, make waits until the load average goes below that limit, or until all the other jobs finish.

### Suppress recipe echoing ###
``` @echo some recipe line ```     
Line starts with @, the echoing of that line is suppressed. 

When make is given '-n' or '--just-print', it echoes recipes without executing them. Even recipe lines starting with @ are printed.

When make is given '-s' or '--slient'. it prevents all echoing.     

The special target .SILENT without prerequisites has the same effect.   

### Conditional functions ###

```
$(if condition,then-part[,else-part])
# if condition expands to non-empty string, true; else, false

$(or condition1[,condition2[,condition3..]])  
# each argument is expanded, if any one argument expandsto non-empty, proccessing stops and the result of the expansion is that string. Else, the result of expansion is empty.

$(and condition1[,condition2[,condition3...]]) 
# each argument is expanded, if any one argument expands empty, processing stop and the result of the expansion is empty. Else, the result of the expansion is the last argument 

```

### Two Flavors of Variable ###

1. Recursively expanded variable  

```
 a = $(b)
 b = c
 
 all:;echo $(a)  # print c
 
```

Disadvantage: 

```
CFLAGS = $(CFLAGS) -O  # this will cause an infinite loop 
```

It will be executed every time the variable is expanded and thus make run slower. 

2. Simply expanded variable 

The actual value of the simply expanded variable is the result of expanding the text that you write. It does not contain any references to other variables; it contains their values as of the time this variable was defined. They work like variables in programming languages. 

Leading whitespaces are discarded but trailing whitespaces are not. 

(Conditional assigned variable: ``` a ? = b ``` It only has an effect if b is undefined. A empty variable is still defined.)   

### String Substitution ### 

```  $(subst from, to, text) ```    

```  $(patsubst pattern, replacement, text）  // equivalent to ${var=pattern:replacement} ```     

```  $(strip string) ```    

```  $(findstring find in) ```     

```  $(filter pattern..., text) ```    

```  $(filter out pattern ..., text) ```    

```  $(sort list) ```    

```  $(word n, text) ``` 

```  $(wordlist, s, e, text) ```     

```  $(words text)  ```     

```  $(firstword names...) ```    

```  $(lastword names...) ```    

``` $(foreach var, list, text) ```    

``` $(file op filename[, text]) ```   

### Automatic Variable ###

Automatic variables are set by make after a rule is matched. They provide access to elements from the target and prerequisite lists so you don’t have to explicitly specify any filenames. They are very useful for avoiding code duplication, but are critical when defining more general pattern rules.

There are seven “core” automatic variables:

$@: The filename representing the target.

$%: The filename element of an archive member specification.

$<: The filename of the first prerequisite.

$?: The names of all prerequisites that are newer than the target, separated by spaces.

$^: The filenames of all the prerequisites, separated by spaces. This list has duplicate filenames removed since for most uses, such as compiling, copying, etc., duplicates are not wanted.

$+: Similar to $^, this is the names of all the prerequisites separated by spaces, except that $+ includes duplicates. This variable was created for specific situations such as arguments to linkers where duplicate values have meaning.

$*: The stem of the target filename. A stem is typically a filename without its suffix. Its use outside of pattern rules is discouraged.

In addition, each of the above variables has two variants for compatibility with other makes. One variant returns only the directory portion of the value. This is indicated by appending a “D” to the symbol, $(@D), $(<D), etc. The other variant returns only the file portion of the value. This is indicated by appending an “F” to the symbol, $(@F), $(<F), etc. Note that these variant names are more than one character long and so must be enclosed in parentheses. GNU make provides a more readable alternative with the dir and notdir functions.



\@ suppresses the normal 'echo' of the command that is executed.

\- means ignore the exit status of the command that is executed (normally, a non-zero exit status would stop that part of the build).

 
\+ means 'execute this command under make -n' (or 'make -t' or 'make -q') when commands are not normally executed. See also the POSIX specification for make and also §9.3 of the GNU Make manual.

The + notation is a (POSIX-standardized) generalization of the de facto (non-standardized) mechanism whereby a command line containing ${MAKE} or $(MAKE) is executed under make -n.




