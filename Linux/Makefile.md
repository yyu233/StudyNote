## Makefile ##

### Syntax of Rule ###

```
  target: prerequisite
  <tab>   receipe
```

Make carries out the receipe on prerequisite to create or update the target.

Simple Makefile
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

Clean: 

```
  .PHONY: clean
  clean: 
        -rm  foobar $(objects)
```

A phony target is not a real file, instead it is the name of the receipe when you explicitly request for execution. A phony target is used for avoiding file name conflict or improve performance. 

