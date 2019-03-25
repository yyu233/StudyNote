## Profile ## 

Every enterprise application has many environments like: Dev, Test and Production.    
In Dev, we don't need to check the database consistency, but in Test and Produciton we need.   
Profile hosts the specific configuration for different environment.    

For the @Profile annotation, it can be used on both method and class level. If you use it on method annotated with @Bean in configuration class, only that bean will belong to the profile. If you use it on configuration class, it will be applied to all the beans within the configuration class, if you use it on @Component class, the profile will be applied to the bean represented by that class.

