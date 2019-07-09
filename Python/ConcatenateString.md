## Concatenate String ## 
Strings can be concatenated (glued together) with the + operator, and repeated with *:

```
>>> # 3 times 'un', followed by 'ium'
>>> 3 * 'un' + 'ium'
'unununium'
```

Two or more string literals (i.e. the ones enclosed between quotes) next to each other are automatically concatenated.
```
>>> 'Py' 'thon'
'Python'
```

This feature is particularly useful when you want to break long strings:
```
>>> text = ('Put several strings within parentheses '
...         'to have them joined together.')
>>> text
'Put several strings within parentheses to have them joined together.'
```
If you want to concatenate variables or a variable and a literal, use +:
```
>>> prefix = 'Py'
>>> prefix + 'thon'
'Python'
```
