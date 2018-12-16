## Static vs Final ##

* **Static Variable**  
  * variable belongs to the class
  * initialize before the class is instantiated
  * a single copy shared by all instances
  
* **Static Method**   
  * static method belongs to the class
  * can only access static variable unless it creates an instance of class
  * can only call static method unless it creates an instances of class
  * can not refer **this** or **super**
  
* **Final Class**  
  * can not be subclassed. This is done for security and efficiency. E.g. Java.lang.String
  
* **Final Method**
  * can not be overidden.

* **Final Variable**
  * can only be assigned once. Don't need to be initialized at the point of declaratoin. 
