## Easier to ask for forgiveness than permission ## 

Worse (LBYL 'look before you leap'):

```
#check whether int conversion will raise an error
if not isinstance(s, str) or not s.isdigit:
    return None
elif len(s) > 10:    #too many digits for int conversion
    return None
else:
    return int(str)
```

Better (EAFP: Easier to ask for forgiveness than permission):

```
try:
    return int(str)
except (TypeError, ValueError, OverflowError): #int conversion failed
    return None
```
