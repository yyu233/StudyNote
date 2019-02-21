## Grep OR ##

``` grep 'PATTERN1\ | PATTERN 2' file ```

## Grep AND ##

```grep -E 'PATTERN1.*PATTERN2' file``` (exact order)  
```grep -E 'PATTERN1.*PATTERN2 | PATTERN2.*PATTERN1' file``` (any order)   

## Grep NOT ##

```grep -v 'PATTERN1' file ```
