## Raw String ## 

If you don’t want characters prefaced by \ to be interpreted as special characters, you can use raw strings by adding an r before the first quote.

```
>>> print('C:\some\name')  # here \n means newline!
C:\some
ame
>>> print(r'C:\some\name')  # note the r before the quote
C:\some\name
```
