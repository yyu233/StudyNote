## Makefile ##

### Syntax of Rule ###

```
  target: prerequisite
  <tab>   receipe
```
A target can be executable, object file, and **action**. 

Tab for each line of receipe to distinguish receipe from other lines. 

Make carries out the receipe on prerequisite to create or update the target.

Recompilation must be done if any of the prerequisites is more recent than the object file or the object file does not exist.   
Simple Makefile

``` include ``` directive tells *make* to suspend readig the current makefile and read other makefile before continuing. 

``` -include ``` directibe will ignore non-existent makefile without throwing warning or error. 

Normal method for preventing  *make* from implicit rule look up for efficieny: use empty receipe.   

One target can be only associated with one receipe in one makefile.   

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
If you write a rule whose receipe never creates a target file, this rule will always be executed every time when the target file does not exist. If the target file exists, for example a file named *clean*, since the clean does not have prerequisites in the rule, clean would always be considered as updated, and the rule will not be executed.
Clean: 

```
  .PHONY: clean
  clean: 
        -rm  foobar $(objects)
```

A phony target is not a real file, instead it is the name of the receipe when you explicitly request for execution. A phony target is used for avoiding file name conflict or improve performance (implicit rule search is skipped). It should not be a prerequisite of a real target file, otherwise its receipe will be run every time make goes to update that file. 


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

Make search for implicit rule for each target without receipe.   
Explicit rule does not influence implict rule search. For example:
```
  foo.o: foo.p 
```

If foo.c exists, then the implicit rule to make foo.o by C compiler is used. 

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
