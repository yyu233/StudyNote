```
def accumulate():
   sm = 0
   while True:
      n = (yield sm) # receive from send and emit sm
      print (f'I got {n} in accumulate and sm ={sm}')
      sm+=n
```
