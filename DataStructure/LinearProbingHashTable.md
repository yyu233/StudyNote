## Linear Probing Hash Table ##

1. Put key and value pairs in 2 separate arrays   
2. If key collision happens, put key in the next empty slot
3. Array length m must be greater than the number of keys n

## Java Implementation ##

```
public class LinearProbingHashTable<Key, Value> {
    private int m = 32678;
    private Key[] keys = (Key[]) new Object[m];
    private Value[] vals = (Value[]) new Object[m];
    
    private int hash(Key key) {
        return (key.hashCode() & 0x7fffffff) % m;
    }
    public Value get(Key key) {
        for (int i = hash(key); keys[i] != null; i = (i + 1) % m) {
            if (keys[i].equals(key)) {
                return vals[i];
            }
        }
        return null
    }
    public void put(Key key, Value val) {
        int i;
        for (i = hash(key); key[i] != null; i = (i + 1) % m) {
            if (keys[i].equals(key)) {
                break;
            }
        }
        keys[i] = key;
        vals[i] = val;
    }
}
```
