## Separate Chaining Hash Table ##

```
 public class SeparateChainingHashTable {
    private int m = 128;
    private Node[] st = new Node[m];
        
    private static class Node {
        private Object key;
        private Object val;
        private Node next;
        
        private Node(Object key, Object val, Node next) {
            this.key = key;
            this.val = val;
            this.next = next;
        }
    }
    
    private int hash(Key key) {
        return (key & 0x7fffffff) % m;
    }
    public Value get(Key key) {
        int i = hash(key);
        for (Node n = st[i]; n != null; n = n.next) {
            if (n.key.equals(key)) {
                return (Value)n.val;
            }
        }
        return null;
    }
    public void put(Key key, Value val) {
        int i = hash(key);
        for (Node n = st[i]; n != null; n = n.next) {
            if (n.key.equals(key)) {
                n.val = val;
                return;
            }
        }
        st[i] = new Node(key, val, st[i]);
    }
 }
```
