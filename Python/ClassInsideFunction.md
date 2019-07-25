**Disadvantages**:    
* Readability: either the class is really trivial or the function inevitably grows quite long and its logic is lost in the class declaration. Also you have an extra level of indentation which might hurt readability if you have some nested loops somewhere
* Performance: the class will be re-costructed at every function call. This usually wont take a huge amount of time, but it will cost a bit. If the function you are running is fast this cost may be significant.


**Advantages**:    
* Locality: you are generally pretty sure that the class wont be used outside the function, in ways you didn't expect
* Performance: looking up a local variable is significantly faster then looking up a global variable. If you create a big number of instances this might improve performance with respect to using a global class. However it's really really easy to counter this advantage via default arguments/local variables.
