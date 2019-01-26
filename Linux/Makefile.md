## Makefile ##

### Syntax of Rule ###

```
  target: prerequisite
  <tab>   receipe
```

Make carries out the receipe on prerequisite to create or update the target.

Simple Makefile
```
  foobar: foobar.h
  <tab>  cc -o foobar.c
```
