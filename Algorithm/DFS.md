## DFS ## 

Graph is represented in Adjacent-List. 

Graph API

|method|meaning|
|---|---|
|public int V()|return the number of vertices|
|public int E()|return the number of edges|
|public void addEdge(int v, int w) |add a new edge to the adjacent list|
|public Iterable<Integer> adj(int v) | return the adjacent list of vertex v |

1. DFS for connected graph produces tree
2. Represent the spanning tree of graph in parent-link 
3. Trace the path from v to s by iterating the parent-link

Implementation: 
```
public class DFS {
  private boolean[] marked;
  private int[] parentLink;
  privage Graph graph;
  private final int s;
  
  public DFS(Graph G, int s) {
    graph = G;
    this.s = s;
    marked = new boolean[graph.V()];
    parentLink = new int[graph.V()];
    dfs(s);
  }
  
  private void dfs(int s) {
    marked[s] = true;
    for (int w: graph.adj(s)) {
      if (!marked[w]) {
        parentLink[v] = w;
        dfs(w);
      }
    }
  }
  public boolean hasPathTo(int v) {
    return marked[v];
  }
  public Iterable<Integer> pathTo(int v) {
    if (!hasPathTo(v)) return null;
    Stack<Integer> path = new Stack();
    for (int x = v; v != s; x = parentLink[x]) {
      path.push(x);
    }
    path.push(s);
    return path;
  }
}
```
