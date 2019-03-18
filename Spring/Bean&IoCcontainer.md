## Bean & IoC container ##
Instead of constructing dependencies by itself, an object can retrieve its dependencies from an IoC container. All we need to do is to provide the container with appropriate configuration metadata.

```
@Component 
public class Bank {

}

@Configuration
@ComponentScan(basePackageClasses = Bank.class)
public class Config {
    @Bean 
    public Account openAccount() {
        return new Account(1000);
    }
}

//Create IoC container
ApplicationContext context = new AnnotationConfigApplicationContext(Config.class);
```


The configuration class produces a bean of type Address. It also carries the @ComponentScan annotation, which instructs the container to looks for beans in the package containing the Bank class.

When a Spring IoC container constructs objects of those types, all the objects are called Spring beans as they are managed by the IoC container.
