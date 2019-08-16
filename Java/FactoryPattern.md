When to Use:
* The client is independent of how we create and compose the objects in the system
* The system consists of multiple families of objects, and these families are designed to be used together
* We need a run-time value to construct a particular dependency

```
package org.opensource.demo.factory;

public class OpenSourceFactory {
    
    public OpenSourceJVMServers getServerByVendor([String][18] name) {
        if (name.equals("Apache")) {
            return new Tomcat();
        } else if (name.equals("Eclipse)) {
            return new Jetty();
        } else if (name.equals("RedHat")) {
            return new WildFly();
        } else {
            return null;
        }
    }
}

public interface OpenSourceJVMServers {
    public void startServer();
    public void stopServer();
    public [String][18] getName();
}

public class WildFly implements OpensourceJVMServers {
    public void startServer() {
        [System][19].out.println("Starting WildFly Server...");
    }

    public void stopServer() {
        [System][19].out.println("Shutting Down WildFly Server...");
    }
    
    public [String][18] getName() {
        return "WildFly";
    }
}
```
