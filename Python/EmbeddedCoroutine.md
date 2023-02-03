```
def wrapper(coroutine):
   coroutine.send(None) # kickstart
   while True:
      try:
         x = (yield)       # capture what is sent...
         coroutine.send(x) # ... and pass it thru
      except StopIteration:
         pass
```
