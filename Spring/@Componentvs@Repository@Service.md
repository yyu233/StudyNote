* @Component is a generic stereotype for any Spring-managed component    
* @Service annotates classes at the service layer   
* @Repository annotates classes at the persistence layer, which will act as a database repository   

### @Component ###
We can use @Component across the application to mark the beans as Spring’s managed components. Spring only pick up and registers beans with @Component  and doesn’t look for @Service and @Repository in general.

### @Repository  ###

@Repository’s job is to catch persistence specific exceptions and rethrow them as one of Spring’s unified unchecked exception.

For this Spring provides PersistenceExceptionTranslationPostProcessor, that requires to add in our application context:
```
<bean class="org.springframework.dao.annotation.PersistenceExceptionTranslationPostProcessor"/>
This bean post processor adds an advisor to any bean that’s annotated with @Repository.
```

### @Service ###

We mark beans with @Service to indicate that it’s holding the business logic. So there’s no any other specialty except using it in the service laye

