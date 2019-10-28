
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
