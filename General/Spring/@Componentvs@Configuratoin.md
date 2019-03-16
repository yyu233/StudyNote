@Configuration classes are just like regular @Components classes, except that methods annotated with @Bean are used to factory beans. Note that a @Component with @Bean annotated methods works the same way, except that scopes are not respected and the @Bean methods are re-invoked (no caching in play), so @Configuration is preferred, even though it requires CGLIB

Here is difference with full example :-
```
//@Configuration or @Component
public static class Config {
    @Bean
    public A a() {
        return new A();
    }
    //**please see a() method called inside b() method**
    @Bean
    public B b() {
        return new B(a());
    }
}
```
1) Here if Config class annotated with @configuration , than a() method and b() method , both will be called once .

2)Here if Config class annotated with @component , than a() method will be called once but b() method will be called twice .

Problem in (2) :- since we have noticed the problem with @compenent annotation . This second configuration (2) is totally incorrect because spring will create a singleton bean of A, but B will obtain another instance of A which is out of the spring context control.

Solution :- we can use @autowired annotation with @component annotation inside Config class .
```
@Component
public static class Config {
    @Autowired
    A a;

    @Bean
    public A a() {
        return new A();
    }

    @Bean
    public B b() {
        return new B(a);
    }
}
```
