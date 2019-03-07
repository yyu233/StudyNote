## Inversion of Control vs Dependency Injection ## 

Inversion of Control is a principle in software engineering by which the control of objects or portions of a program is transferred to a container or framework. It’s most often used in the context of object-oriented programming.

By contrast with traditional programming, in which our custom code makes calls to a library, IoC enables a framework to take control of the flow of a program and make calls to our custom code. To enable this, frameworks use abstractions with additional behavior built in. If we want to add our own behavior, we need to extend the classes of the framework or plugin our own classes.

The advantages of this architecture are:

decoupling the execution of a task from its implementation
making it easier to switch between different implementations
greater modularity of a program
greater ease in testing a program by isolating a component or mocking its dependencies and allowing components to communicate through contracts

Here’s how you would create an object dependency in traditional programming:
```
public class Store {
    private Item item;
  
    public Store() {
        item = new ItemImpl1();    
    }
}
```
In the example above, we need to instantiate an implementation of the Item interface within the Store class itself.

By using DI, we can rewrite the example without specifying the implementation of Item that we want:
```
public class Store {
    private Item item;
    public Store(Item item) {
        this.item = item;
    }
}
```
