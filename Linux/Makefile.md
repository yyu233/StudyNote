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

A phony target is not a real file, instead it is the name of the receipe when you explicitly request for execution. A phony target is used for avoiding file name conflict or improve performance. 


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
