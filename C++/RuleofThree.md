## Rule of Three ## 

If a class defines one of the following it should probably explicitly define all three: 
* destructor 
* copy constructor 
* copy assignment operator 

If they are not implemented by programmer, they will be implicitly implemented by the compiler with the following default semantics: 
* Destructor: call the destructors of all the object's class-type members  
* Copy constructor: construct all the object's members from the corresponding members of the copy contructor's argument, calling the copy assignment operators of the object's class-type memebers, and doing a plain assignment of all non-class type data members. 
