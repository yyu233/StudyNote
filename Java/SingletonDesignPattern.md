## Singleton Design Pattern ## 

Singleton Pattern says that just"define a class that has only one instance and provides a global point of access to it".

* Early Instantiation: creation of instance at load time.
* Lazy Instantiation: creation of instance when required.

**Advantage of Singleton design pattern**:   
Saves memory because object is not created at each request. Only single instance is reused again and again.   
**Usage of Singleton design pattern**:  
Singleton pattern is mostly used in multi-threaded and database applications. It is used in logging, caching, thread pools, configuration settings etc.   


```
class Singleton {
    private static Singleton a = new Singleton();
    
    private Singleton(); 
    
    public static Singleton getSingelton() {
        return a;
    }
    
    public void someMethod(){ 
        //do something
    }
}
```

```
class Singleton {
    private static Singleton a;
    
    private A();
    
    public static Singleton getSingleton() {
        if (a == null) {
            synchronized(Singleton.class) {
                if (a == null) {
                    a = new Singleton();
                }
            }
        }
        
        return a;
    }
    
    public void someMethod() {
      //do something
      
    }
}

```
