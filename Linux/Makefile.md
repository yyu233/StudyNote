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
