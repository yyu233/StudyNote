## Adjacent-list Graph ##
Two things need to be considered for graph processing: 
1. Sufficient space to represent the type of graphs we encounter in applications. 
2. Time-efficient implementation of graph instance method. 

### Java Applicaton ###

```
public class Graph {
    private final int V;
    private Bag<Integer>[] adj;
    
    public Graph(int V) {
        this.V = V;
        adj = (Bag<Integer>[]) new Bag[V];
        for (int v = 0; v < V; v++) {
            adj[v] = new Bag<Integer>();
        }
    }
    
    public void addEdge(int v, int w) {
        adj[v].add(w);
        adj[w].add(v);
    }
    public Iterable<Integer> adj(int v) {
        return adj[v];
    }
}
```
