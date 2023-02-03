```
def flatten(seq):
   for item in seq:
      if hasattr(item,'__iter__'):
         yield from flatten(item)
      else:
         yield item

```
