## Scope ##

Bean definition is a receipe. You can have many object instances created from a single bean. Use @Scope to control the number of object instances created from a bean. 

Scope	Description  
**singleton**

Scopes a single bean definition to a single object instance per Spring IoC container.

**prototype**

Scopes a single bean definition to any number of object instances.

**request**

Scopes a single bean definition to the lifecycle of a single HTTP request; that is each and every HTTP request will have its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring ApplicationContext.

**session**

Scopes a single bean definition to the lifecycle of a HTTP Session. Only valid in the context of a web-aware Spring ApplicationContext.

**global session**

Scopes a single bean definition to the lifecycle of a global HTTP Session. Typically only valid when used in a portlet context. Only valid in the context of a web-aware Spring ApplicationContext.
