## Decorator ##

Python decorator is a function that helps to add some additional functionalities to an already defined function. Python decorator is very helpful to add functionality to a function that is implemented before without making any change to the original function. Decorator is very efficient when want to give an updated code to an existing code.   
It helps keeping our code **loosely coupled** with the client code

Any sufficiently generic functionality you can “tack on” to an existing class or function’s behavior makes a great use case for decoration. This includes:
* logging
* enforcing access control and authentication
* instrumentation and timing functions
* rate-limiting
* caching

Order of decorators is applied from bottom to top.     
This also means that deep levels of decorator stacking will have an effect on performance eventually because they keep adding nested function calls. Usually this won’t be a problem in practice, but it’s something to keep in mind if you’re working on performance intensive code.     
[Reference](https://www.journaldev.com/14893/python-property-decorator)    
[Reference](https://dbader.org/blog/python-decorators)
