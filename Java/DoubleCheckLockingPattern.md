
```
public class Singleton {
  
  private volatile static Singelton instance;
  
  private Singleton () {}
  
  public static Singleton() {
      if (instance == null) {
          synchronized(Singleton.class) {
              if (instance == null) {
                  instance = new Singleton();
              }
          }
      }
      return instance;
  }
}

```

[History](https://blog.csdn.net/chenchaofuck1/article/details/51702129)
