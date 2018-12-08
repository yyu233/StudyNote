 ## Queue ## 
 
 FIFO 
 
### Application ###
1. BFS
2. CPU scheduling
3. Process communication (data does not arrive at the same rate)

### Java API ###

* void offer(Item item)
* String pull()
* String peek()

### Implememt Queue with two stacks 

```
 class Queue {
   private Stack<Item> s1 = new Stack<>();
   private Stack<Item> s2 = new Stack<>();
   
   public void offer(Item item) {
      s1.push(item);
   }
   public Item pull() {
     if (s2.empty()) {
       if (s1.empty()) {
         return null;
       }
       while (!s1.empty()) {
         s2.push(s1.pop());
       }
     }
     return s2.pop();
   }
 }
 ```


