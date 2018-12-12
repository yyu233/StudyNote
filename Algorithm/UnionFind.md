## Union Find ##

### Dynamic Connectivity Problem ###

The problem is defined on an undirected graph with N vertices. 
There are two operations: 1. add an edge  2. detect connectedness. 

We can partitioin the vertices into sets. Each vertice is in exactly one set. Two vertices are connected if they are in the same set. 

### Java Implementation ###

```
  public class UF {
      private int[] comp;
      private int count;
      
      public UF(int size) {
        this.comp = new int[size];
        this.count = size;
      }
      
      public int getCount() {
        return count;
      }
      public boolean isConnected(int p, int q) {
        return find(p) == find(q);
      }
      public int find(int id) {
        return comp[id];
      }
      public void union(int p, int q) {
        int pComp = count[p];
        int qComp = count[q];
        for (int i = 0; i < count.length; i++) {
          if (count[i] = pComp) {
            comp[i] = qComp;
          }
          count--;
        }
      }
  }
```
