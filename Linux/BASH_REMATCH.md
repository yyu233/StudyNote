If the expression matches the string, the matched part of the string is stored in the BASH_REMATCH array.
Parts of the matched string
Enclosing part of the regular expression in ()-s makes the matched substring available in the subsequent entries in the BASH_REMATCH array:

```
[[ "abcdef" =~ (b)(.)(d)e ]]

# Now:
#   BASH_REMATCH[0]=bcde
#   BASH_REMATCH[1]=b
#   BASH_REMATCH[2]=c
#   BASH_REMATCH[3]=d 
```
